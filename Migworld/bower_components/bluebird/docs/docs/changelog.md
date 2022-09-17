---
id: changelog
title: Changelog
---

## 3.3.4

Features:

 - Warnings about created promises that are not returned are no longer given if the handler promise has not been chained. This should reduce the amount of false positives with this warning.

## 3.3.3

Bugfixes:

 - Fix stack overflow error when a promise returned by promisified function rejects early in a huge array when using [Promise.mapSeries](.) or [Promise.each](.)


## 3.3.2

Bugfixes:

 - Fix missing newline in stack trace reported by [.done()](.) ([#1020](.)).
 - Detect deep circular resolutions

## 3.3.1

Bugfixes:

 - Fix crash when cancelling a [.tap()](.) handler promise ([#1006](.)).

## 3.3.0

Features:

 - Cancelling Promise returned from [Promise.delay()](.) and [.delay()](.) now calls `clearTimeout` ([#1000](.))
 - Add [monitoring and lifecycle hooks](http://bluebirdjs.com/docs/features.html#promise-monitoring)
 - Add `'warning'` hook for warnings ([#980](.))

Bugfixes:

 - Fix warnings for "promise was rejected with non-error" being output when promises are rejected with errors from different realm ([#990](.))


## 3.2.2

Bugfixes:

 - Make build script's output work without TTY

## 3.2.1

Bugfixes:

 - Revert monitoring feature due to crash in browser


## 3.2.0

- Broken build

## 3.1.5

Dummy release to trigger CDN update.

## 3.1.4

Bugfixes:

 - Fix broken npm prepublish script release


## 3.1.3

Bugfixes:

 - Fix generators crashing in node 0.12 ([#978](.))
 - Add minimal build files to build ([#976](.), [#757](.))

## 3.1.2

Features:

 - [.timeout()](.) now `clearTimeout`s the timer if the resulting promise is cancelled ([#926](.))
 - [Promise.coroutine](.) now returns function with same `.length` as the original function ([#927](.), [#933](.))

Bugfixes:

 - Fix long stack traces not working when promise is created from [Promise.fromCallback](.) ([#971](.))
 - Fix [.finally()](.) handlers not being called when promise is cancelled while a domain is active ([#963](.))
 - Fix [.timeout()](.) trying to cancel a promise even if cancellation is disabled ([#970](.))

## 3.1.1

Bugfixes:

 - Disable wForgottenWarning when all warnings are disabled


## 3.1.0

Features:

 - Added ability to configure the [forgotten return statement](http://bluebirdjs.com/docs/warning-explanations.html#warning-a-promise-was-created-in-a-handler-but-none-were-returned-from-it) warning separately \([#920](.)\).

Bugfixes:

- Fixed the bug where returning a value from [.finally](.) or [.tap](.) handler did not make a warning about a forgotten return go away \([#846](.)\).
- Fixed the bug where setTimeout is used in Chrome instead of MutationObserver \([#915](.)\)
- Fixed the bug where using [.bind](.) suppressed unhandled rejections \([#841](.)\)

## 3.0.6

Bugfixes:

 - Fix [.timeout()](.) not cancelling parent \([#891](.)\)
 - Fix long stack traces when using [Promise.resolve()](.) \([#861](.)\)
 - Fix [Promise.config()](.) not disabling long stack traces when passing `longStackTraces: false` \([#897](.)\)

## 3.0.5

Bugfixes:

 - Added [forgotten return warnings](http://bluebirdjs.com/docs/warning-explanations.html#warning-a-promise-was-created-in-a-handler-but-none-were-returned-from-it)  to [Promise.try](.) and [Promise.method](.)

## 3.0.4

Bugfixes:

 - The stack trace for [forgotten return warnings](http://bluebirdjs.com/docs/warning-explanations.html#warning-a-promise-was-created-in-a-handler-but-none-were-returned-from-it) is more useful now.


## 3.0.3

Bugfixes:

 - 3rd party libraries rejecting promises with non-errors no longer causes warnings
 - When `NODE_ENV` environment variable is `"development"` setting `BLUEBIRD_DEBUG` environment variable to `0` can now be used to disable debug mode

## 3.0.2

Bugfixes:

 - Fix crash when using node.js domains [#829](.)

## 3.0.1 (2015-10-28)

See [New in 3.0](new-in-bluebird-3.html).

## 3.0.0

See [New in 3.0](new-in-bluebird-3.html).
