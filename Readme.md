## Installation

### Gradle wrapper

```bash
gradle wrapper --gradle-version 7.6 --distribution-type all
```

## plugins
plugins define every thing about the tasks

### java plugin 
build and run java packages, enough for library project 

### application plugin 
for making an executable application 

1. using application plugin
```groovy
 plugins {
    id 'application'
}
```

2. setting main class.
```groovy
application {
    mainClass = 'com.wrapper.WrapperApplication'
}
```

3. updating the jar task.
```groovy
tasks.jar {
    manifest {
        attributes("Main-Class": application.mainClass)
    }
}
``` 

## Caching 
faster builds by reusing the outputs from the last/ any earlier build 

```shell
./gradlew build --build-cache
```

## Dependency management

### default resolution 
from the set of all requested versions (direct dependencies, transitive dependency and constrains), gradle will default to the highest available

## using constrains 
1. declare the version for the dependency if not declared already.
2. downgrade the version of the transitive dependency.    
```groovy
dependencies {
    testImplementation 'org.junit.jupiter:junit-jupiter-api'

    constraints {
        testImplementation("org.junit.jupiter:junit-jupiter-api:5.7.0"){
            because("Newer incompatible version")
        }
    }
}
```


 

 