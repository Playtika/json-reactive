[![CircleCI](https://circleci.com/gh/Playtika/json-reactive/tree/develop.svg?style=shield&circle-token=dc125176af2f7746808d5335de63f214f6dab7ae)](https://circleci.com/gh/Playtika/json-reactive/tree/develop)
[![codecov](https://codecov.io/gh/Playtika/json-reactive/branch/develop/graph/badge.svg)](https://codecov.io/gh/Playtika/json-reactive)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.playtika.reactivejson/json-reactive/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.playtika.reactivejson/json-reactive)

# json-reactive

Use Json Reactive to make POJO binding reactively 

## Overview

Implementation of reactive json object reader over Jackson non blocking json parser.

## Modules
  
  **_json-nonblocking_** : non blocking implementation that can be wrapped with any reactive approach
  
  **_json-reactor_** : io.projectreactor implementation 
  
  **_json-rx2_** : rxJava2 implementation
  
## Usage io.projectreactor 

```java
ReactorObjectReader reader = new ReactorObjectReader(new JsonFactory());

Flux<TestEntity> testEntityRed = reader.readElements(byteBuffers, objectMapper.readerFor(TestEntity.class));
```

## Usage rxJava2 

```java
Rx2ObjectReader reader = new Rx2ObjectReader(new JsonFactory());

Flowable<TestEntity> testEntityRed = reader.readElements(byteBuffers, objectMapper.readerFor(TestEntity.class));
```

## Maven

```xml
...
<dependencies>
    ...

    <dependency>
        <groupId>com.playtika.reactivejson</groupId>
        <artifactId>json-reactor</artifactId>
        <version>PICK LATEST</version>
    </dependency>

    or if you tend to use Rx2 interfaces

    <dependency>
        <groupId>com.playtika.reactivejson</groupId>
        <artifactId>json-rx2</artifactId>
        <version>PICK LATEST</version>
    </dependency>
    ...
</dependencies>
```
