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

### 1. Add GitHub Packages registry to your root `settings.gradle`:

```groovy
dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()
        maven {
            url = uri("https://maven.pkg.github.com/epsilondelta-speed/orion-flutter-aar")
            credentials {
                username = project.findProperty("gpr.user") ?: System.getenv("USERNAME_GITHUB")
                password = project.findProperty("gpr.key") ?: System.getenv("TOKEN_GITHUB")
            }
        }
    }
}
