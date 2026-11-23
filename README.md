# SuperPI Maven

[简体中文](README.cn.md) | English

Static read-only Maven repository served via GitHub Pages at **`https://sadami3066.github.io/SuperPI-Maven`**. Published automatically by CI workflows from [`Sadami3066/SuperPI`](https://github.com/Sadami3066/SuperPI) and [`Sadami3066/SuperPI-KotlinSDK`](https://github.com/Sadami3066/SuperPI-KotlinSDK); do not hand-edit files under `io/`.

## Coordinates

| Artifact | Latest | Source Repository |
|---|---|---|
| `io.github.sadami3066.superpi:plugin-api` | `2.0.1` | [`SuperPI` (`apps/android/plugin-api`)](https://github.com/Sadami3066/SuperPI) |
| `io.github.sadami3066.superpi:design` | `1.0.0` | [`SuperPI` (`apps/android/design`)](https://github.com/Sadami3066/SuperPI) |
| `io.github.whywood.superpi.sdk:pi-coding-agent-android` | `0.7.0` | [`SuperPI-KotlinSDK`](https://github.com/Sadami3066/SuperPI-KotlinSDK) |
| `io.github.whywood.superpi.sdk:pi-ai` / `pi-agent` / `pi-mcp` (`-android` / `-jvm`) | `0.7.0` | [`SuperPI-KotlinSDK`](https://github.com/Sadami3066/SuperPI-KotlinSDK) |

## Gradle Configuration

In your plugin project (`settings.gradle.kts` & `build.gradle.kts`):

```kotlin
// settings.gradle.kts
dependencyResolutionManagement {
    repositories {
        maven("https://sadami3066.github.io/SuperPI-Maven") {
            content {
                includeGroup("io.github.sadami3066.superpi")
                includeGroup("io.github.whywood.superpi.sdk")
            }
        }
        google()
        mavenCentral()
    }
}
```

```kotlin
// External .ddp plugins MUST use compileOnly (the host app provides these classes at runtime)
dependencies {
    compileOnly("io.github.sadami3066.superpi:plugin-api:2.0.1")
}
```

For full plugin setup, `plugins/template/`, and ABI rules, see [SuperPI Plugin Developer Docs](https://github.com/Sadami3066/SuperPI/blob/main/docs/plugins/README.md).

## License

- `io.github.sadami3066.superpi:*` (`plugin-api`, `design`): [Apache-2.0](LICENSE)
- `io.github.whywood.superpi.sdk:*`: MIT (see [SuperPI-KotlinSDK](https://github.com/Sadami3066/SuperPI-KotlinSDK/blob/main/LICENSE))
