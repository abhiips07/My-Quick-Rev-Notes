# Gradle

## Features:

- flexibility
- incremental builds and cache mechanisms
- support projects with multiple languages

## References
- `${VARIABLE}` will get its value from **gradle.properties** or environment variable
- `build.gradle` file is the main build script
- `settings.gradle` contains configuration settings. It may specify the project name, include additional build scripts, or define multi-project builds.
- `gradle.properties` in user folder or project folder. Contains gradle settings, variable and environment values

## Directory structure
```
src/main/java/
src/main/resources/
src/test/java/
src/test/resources/

build/

gradle/gradle-wrapper.jar
gradle/gradle-wrapper.properties

build.gradle
gradle.properties
settings.gradle
```

## build.gradle syntax

```groovy
plugins {
	id 'java'
	id 'resources
	testjava'
	testresources

	id 'checkstyle'
	id 'findbugs'
}

repositories {
	mavenCentral()
}

repositories {
	//  another popular public repository maintained by Bintray
	jcenter()
}

repositories {
	// contains Android libraries, Google APIs, and other Google-related artifacts
	google()
}

repositories {
	// custom repository
	maven {
		url 'https://my-custom-repo.com/repository/maven-public/'
		credentials {
			username 'your-username'
			password 'your-password'
		}
	}
}


dependencies {
	implementation 'com.example:library:1.0.0'
	// Add more dependencies as needed
}

task customTask {
	// Define task actions here
}

// ***** Define Variable *****
ext {
    myVariable = 'value'
    anotherVariable = 42
}
// OR
def myVariable = 'value'
```

## Run Gradle commands

- `gradle build`: This command compiles and assembles your project. It executes tasks such as compiling source code, running tests, and packaging artifacts.
- `gradle test`: This command runs tests in your project.
- `gradle run`: If your project has an executable entry point, you can use this command to run it.
- `gradle <task>`: Replace \<task\> with the name of a specific task defined in your build.gradle file to execute that task.

# Maven

## Features:
- Conventional approach, directory structure and naming convention
- Large ecosystem and standardization

## References
- `pom.xml`: Contains project-specific configurations, dependencies, plugins, and other settings.
- `settings.xml`: in user folder or project folder. Contains global configuration settings for Maven, such as repository configurations, proxy settings, and profiles.

## Directory structure
```
src/main/java/
src/main/resources/
src/test/java/
src/test/resources/

target/

mvn/wrapper/maven-wrapper.properties

pom.xml
settings.xml
```
## pom.xml syntax

## Maven lifecycle
