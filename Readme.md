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
