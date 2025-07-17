# orion-flutter-aar
📦 Orion Flutter — Android Flutter Plugin - Performance Monitoring SDK
# Orion Flutter AAR

This repository contains the compiled Android `.aar` artifact for the [Orion Flutter Plugin](https://github.com/epsilondelta-speed/orion_flutter_test1), used to integrate the Orion performance monitoring SDK into Flutter apps.

---

## 📦 What is this?

The `.aar` (Android Archive) in this repository is a prebuilt binary of the Orion SDK tailored for hybrid Flutter apps. It enables you to:

- Monitor **screen performance** (TTID, TTFD, janky frames, frozen frames).
- Track **network requests** per screen.
- Capture **unhandled Dart errors** and native Android crashes.
- Integrate Orion without bundling full Kotlin source in your main app repo.

---

## 🔧 Usage

### 1. Groovy (build.gradle)

```groovy
// Top-level build.gradle
allprojects {
    repositories {
        google()
        mavenCentral()
        maven {
            name = "GitHubPackages"
            url = uri("https://maven.pkg.github.com/epsilondelta-speed/orion-flutter-aar")
            credentials {
                username = project.findProperty("gpr.user") ?: System.getenv("USERNAME")
                password = project.findProperty("gpr.key") ?: System.getenv("GITHUB_TOKEN")
            }
        }
    }
}

// app/build.gradle
dependencies {
    implementation "co.epsilondelta:orion-flutter:1.0.0"
}
```
### 1. Kotlin DSL (build.gradle)
```kotlin
// Top-level build.gradle.kts
allprojects {
    repositories {
        google()
        mavenCentral()
        maven {
            name = "GitHubPackages"
            url = uri("https://maven.pkg.github.com/epsilondelta-speed/orion-flutter-aar")
            credentials {
                username = project.findProperty("gpr.user") as String? ?: System.getenv("USERNAME")
                password = project.findProperty("gpr.key") as String? ?: System.getenv("GITHUB_TOKEN")
            }
        }
    }
}

// module-level build.gradle.kts
dependencies {
    implementation("co.epsilondelta:orion-flutter:1.0.0")
}

```
