Kotlin Coroutine (Experimental) Adapter
=======================================

A Retrofit 2 `CallAdapter.Factory` for [Kotlin coroutine's][1] `Deferred`.


Usage
-----

Add `KotlinCoroutineCallAdapterFactory` as a `Call` adapter when building your `Retrofit` instance:
```kotlin
val retrofit = Retrofit.Builder()
    .baseUrl("https://example.com/")
    .addCallAdapterFactory(KotlinCoroutineCallAdapter())
    .build()
```

Your service methods can now use `Deferred` as their return type.
```kotlin
interface MyService {
  @GET("/user")
  fun getUser(): Deferred<User>

  // or

  @GET("/user")
  fun getUser(): Deferred<Response<User>>
}
```


Download
--------

Download [the latest JAR][2] or grab via [Maven][3]:
```xml
<dependency>
  <groupId>com.jakewharton.retrofit</groupId>
  <artifactId>retrofit2-kotlin-coroutines-experimental-adapter</artifactId>
  <version>latest.version</version>
</dependency>
```
or [Gradle][3]:
```groovy
compile 'com.jakewharton.retrofit:retrofit2-kotlin-coroutines-experimental-adapter:latest.version'
```

Snapshots of the development version are available in [Sonatype's `snapshots` repository][snap].


License
=======

    Copyright 2017 Jake Wharton

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.




 [1]: https://kotlinlang.org/docs/reference/coroutines.html
 [2]: https://search.maven.org/remote_content?g=com.squareup.retrofit2&a=adapter-kotlin-coroutines-experimental&v=LATEST
 [3]: http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.squareup.retrofit2%22%20a%3A%22adapter-kotlin-coroutines-experimental%22
 [snap]: https://oss.sonatype.org/content/repositories/snapshots/