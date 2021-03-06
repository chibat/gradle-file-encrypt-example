# gradle-file-encrypt plugin example

[![Build Status](https://travis-ci.org/chibat/gradle-file-encrypt-example.svg?branch=master)](https://travis-ci.org/chibat/gradle-file-encrypt-example)

This repository is a example for gradle-file-encrypt plugin.

* https://github.com/CherryPerry/GradleFileEncrypt
* https://plugins.gradle.org/plugin/com.cherryperry.gradle-file-encrypt

## decrypt

```
$ git clone https://github.com/chibat/gradle-file-encrypt-example.git
$ cd gradle-file-encrypt-example
$ echo "gfe.password=pass" > local.properties
$ # or
$ export GFE_PASSWORD=pass
$
$ ./gradlew decryptFiles
$ cat src/main/resources/application-default.yml
password: foo
$ cat src/main/resources/application-production.yml
password: bar
```

## encrypt

```
$ ./gradlew encryptFiles
```

If the command is not completed, set following environment value before 'gradlew'.
```
$ export JAVA_OPTS='-Dsecurerandom.strongAlgorithms=NativePRNGNonBlocking:SUN'
```

## .gitignore

```
### gradle-file-encrypt plugin ###
local.properties

### App Config ###
src/main/resources/application-default.yml
src/main/resources/application-production.yml
```

## Note

* git pull -> gradlew decryptFiles
* gradlew encryptFiles -> git add

