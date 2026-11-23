# SuperPI Maven

[English](README.md) | 简体中文

通过 GitHub Pages 托管的只读静态 Maven 分发仓库：**`https://sadami3066.github.io/SuperPI-Maven`**。本仓库产物由 [`Sadami3066/SuperPI`](https://github.com/Sadami3066/SuperPI) 与 [`Sadami3066/SuperPI-KotlinSDK`](https://github.com/Sadami3066/SuperPI-KotlinSDK) 的 CI 流水线自动推送，请勿手改 `io/` 目录下的发布产物。

## 托管坐标

| 坐标 | 当前版本 | 源码来源 |
|---|---|---|
| `io.github.sadami3066.superpi:plugin-api` | `2.0.1` | [`SuperPI` (`apps/android/plugin-api`)](https://github.com/Sadami3066/SuperPI) |
| `io.github.sadami3066.superpi:design` | `1.0.0` | [`SuperPI` (`apps/android/design`)](https://github.com/Sadami3066/SuperPI) |
| `io.github.whywood.superpi.sdk:pi-coding-agent-android` | `0.7.0` | [`SuperPI-KotlinSDK`](https://github.com/Sadami3066/SuperPI-KotlinSDK) |
| `io.github.whywood.superpi.sdk:pi-ai` / `pi-agent` / `pi-mcp`（`-android` / `-jvm`） | `0.7.0` | [`SuperPI-KotlinSDK`](https://github.com/Sadami3066/SuperPI-KotlinSDK) |

## Gradle 引用配置

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
// 外部 .ddp 插件工程请务必使用 compileOnly（运行时复用宿主类，避免打包冲突）
dependencies {
    compileOnly("io.github.sadami3066.superpi:plugin-api:2.0.1")
}
```

完整的插件模板（`plugins/template/`）、清单字段与兼容规范请查阅 [SuperPI 插件开发文档](https://github.com/Sadami3066/SuperPI/blob/main/docs/plugins/README.md)。

## 开源许可

- `io.github.sadami3066.superpi:*`（`plugin-api`、`design`）：[Apache-2.0](LICENSE)
- `io.github.whywood.superpi.sdk:*`：MIT（详见 [SuperPI-KotlinSDK](https://github.com/Sadami3066/SuperPI-KotlinSDK/blob/main/LICENSE)）
