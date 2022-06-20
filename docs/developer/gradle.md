# Gradle

### Install

```bash
#install java
brew install adoptopenjdk11
java -v
#install gradle
brew install gradle
gradle -v
# view deprecated versions
gradle help --scan
# upgrade
gradle wrapper --gradle-version 7.1.1
```

### Java Application

https://docs.gradle.org/7.1.1/samples/sample_building_java_applications.html

```bash
# create gradle project
mkdir demo
cd demo
gradle init

# test
./gradlew check

# run
./gradlew run

# bundle
./gradlew build

# build scan
./gradlew build --scan

# find tasks
gradle tasks

#learn more of tasks
gradle help --task <taskname>

# run a task
gradle <taskname>

# view structure of multi-project build
gradle -q projects
```

### Java Custom Task as CLI

```kotlin
plugins {
    java
}
repositories {
    mavenCentral()
}
java {
    sourceCompatibility = org.gradle.api.JavaVersion.VERSION_1_8
    targetCompatibility = org.gradle.api.JavaVersion.VERSION_1_8
}
dependencies {
    implementation("io.vertx:vertx-core:3.8.0")
    implementation("ch.qos.logback:logback-classic:1.2.3")
    testImplementation("junit:junit:4.13")
}
tasks.create<JavaExec>("run") {
    main = project.properties.getOrDefault("mainClass", "chapter2.hello.Deployer") as String
    classpath = sourceSets["main"].runtimeClasspath
    systemProperties["vertx.logger-delegate-factory-class-name"] = "io.vertx.core.logging.SLF4JLogDelegateFactory"
}
```

```bash
./gradlew run -PmainClass=chapter2.hello.HelloVerticle
```

### Reference

- https://docs.gradle.org/7.1.1/samples/index.html

- https://spring.io/guides/gs/gradle/
- https://gradle-initializr.cleverapps.io/
- https://github.com/gradle/kotlin-dsl-samples
