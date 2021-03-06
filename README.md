RxJava 2 Extensions
===================

[ ![Download](https://api.bintray.com/packages/sch/maven/rxjava2-extensions/images/download.svg) ](https://bintray.com/sch/maven/rxjava2-extensions/_latestVersion)

Collection of additional operators and utilities for RxJava 2.

## Usage

```gradle
dependencies {
    implementation "com.github.technoir42:rxjava2-extensions:(insert latest version)"
}
```

## Extensions

| **Extension**                               | **Description**                                                                                                                                                                |
|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Completable.sneakyAwait                     | Like `Completable.blockingAwait` but doesn't wrap checked exceptions in `RuntimeException`.                                                                                    |
| Single.sneakyGet                            | Like `Single.blockingGet` but doesn't wrap checked exceptions in `RuntimeException`.                                                                                           |
| Maybe.sneakyGet                             | Like `Maybe.blockingGet` but doesn't wrap checked exceptions in `RuntimeException`.                                                                                            |
| Single.cacheSuccess                         | Stores success value from the source Single and replays it to observers.                                                                                                       |
| Single.mapError                             | If upstream terminates with an error transforms the error by applying a provided function and terminates with the resulting error instead.                                     |
| Observable.endWith(item)                    | Emits the specified item after it finishes emitting items emitted by the source Observable.                                                                                    |
| Observable.surroundWith(before, after)      | Emits `before`, then items from source, then `after`.                                                                                                                          |
| Observable.pairwiseWithPrevious             | Emits a pair of each upstream element and previous element.                                                                                                                    |
| Observable.valveLatest                      | Relays values until the other `Observable` signals false and resumes when the other `Observable` signals true again. Drops all values except the latest while valve is closed. |
| ConnectableObservable.autoConnectDisposable | Like `ConnectableObservable.autoConnect` but returns `DisposableObservable` whose `dispose` method terminates the connection.                                                  |

## Other

* `FailFastErrorHandler` - RxJava error handler that fails fast on programming errors but ignores normal `UndeliverableException`s.

## License

```
Copyright 2018 Sergey Chelombitko

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
