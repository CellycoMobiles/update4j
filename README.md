# [![update4j-logo][3]][3]

[![Build Status](https://travis-ci.org/update4j/update4j.svg?branch=master)](https://travis-ci.org/update4j/update4j)   [![Apache License](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)   ![Java-9+](https://img.shields.io/badge/java-9%2B-orange.svg)   [![Maven Release](https://img.shields.io/badge/maven%20central-v1.4.5-yellow.svg)](https://search.maven.org/search?q=org.update4j)    [![Gitter](https://badges.gitter.im/update4j/update4j.svg)](https://gitter.im/update4j/update4j?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)


**Read the [documentation](https://github.com/update4j/update4j/wiki/Documentation), explore the [JavaDoc](http://docs.update4j.org/javadoc/update4j/index.html), or [see it in action](https://github.com/update4j/update4j/wiki/Demo-Application)**

_Create a framework_: design the environment and lifecycle (&mdash;bootstrap) to make your own auto-update framework and hack it to the core, or use the built-in default bootstrap.

## Screenshots

### Headless

Using the default bootstrap, downloads 4 files then launches `hello-world.jar`. You can see that subsequent runs won't download again.

[![headless][2]][2]

### JavaFX

Using a custom bootstrap implemented to report progress in JavaFX, downloads 4 files then launches `hello-world.jar`.

[![javafx][1]][1]


## Overview

Update4j is the first auto-update and launcher library designed for Java 9+. Easily host your application files anywhere (even Google Drive, Dropbox, Amazon S3, or Maven Central) and you can synchronize them with all your distributed applications. You can use [any protocol you wish](https://gitter.im/update4j/update4j?at=5c7067c1a378ef11f6236c86) to retrieve those files and may be protected under authenticated API.

In update4j _you_ have ultimate control of every process, from startup - update - launch - shutdown, since it's a library (you call the 3rd party code) not a framework (3rd party calls your code outside your control). In addition, every single piece of code is completely updatable; [even update4j itself](https://github.com/update4j/update4j/wiki/Documentation#updating-update4j-itself), once a new version is released!



## Installation & Usage

You can [download](https://repo1.maven.org/maven2/org/update4j/update4j/1.4.5/update4j-1.4.5.jar) or install using Maven:

```xml
<dependency>
    <groupId>org.update4j</groupId>
    <artifactId>update4j</artifactId>
    <version>1.4.5</version>
</dependency>
```

You can use it as a regular dependency, or you may run it as a runnable JAR file. 

To run it in the modulepath, use either of:

```shell
$ java -p update4j-1.4.5.jar -m org.update4j
$ java -p . -m org.update4j

```

To run it in the classpath, use either of:

```shell
$ java -jar update4j-1.4.5.jar
$ java -cp * org.update4j.Bootstrap
```

For more information refer to [Starting the Application](https://github.com/update4j/update4j/wiki/Documentation#starting-the-application) in the wiki.


## What's New in 1.4.5
  * Added `DynamicClassLoader` and the new [Classloading Model](https://github.com/update4j/update4j/wiki/Documentation#classloading-model).
  * New design reporting download progress in `DefaultUpdateHandler`.
  * Added `SingleInstanceManager::tryExecute` to handle second instance instead of automatic shutdown.
  * Added `FileMapper::getChecksum` and `FileMapper::getSignature`
  * `user.home` and `user.dir` will only be automatically replaced when matched to the beginning of a path.
  * Improved file accessibility check when copying new files to its final location.

## Contributors

  * [@mordechaim](https://github.com/mordechaim) — lead contributor.
  * [@ChristianCiach](https://github.com/ChristianCiach) — tested and inspired many features and bugfixes.
  * [@edvin](https://github.com/edvin) — original author of [edvin/FXLauncher](https://github.com/edvin/fxlauncher) which highly influenced the design of update4j.

## License

This project is licensed under the [Apache Software License 2.0](http://www.apache.org/licenses/LICENSE-2.0)


  [1]: https://i.stack.imgur.com/Hz1G7.gif
  [2]: https://i.stack.imgur.com/Ttf8Z.gif
  [3]: https://i.stack.imgur.com/L6WAF.jpg
