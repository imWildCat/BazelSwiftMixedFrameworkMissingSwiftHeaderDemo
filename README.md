# BazelSwiftMixedFrameworkMissingSwiftHeaderDemo

`generates_header=True` does not work anymore.

## With `0.24.0`

`MixedLangFramework-Swift.h` is generated.

```shell
Target //MixedLangFramework:MixedLangFramework up-to-date:
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/MixedLangFramework
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Modules/MixedLangFramework.swiftmodule/x86_64.swiftmodule
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/MixedLangFramework-Swift.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/DemoManager.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/SwiftLibrary.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/MixedLangFramework-umbrella.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Modules/module.modulemap
INFO: Elapsed time: 6.946s, Critical Path: 6.62s
INFO: 9 processes: 3 internal, 5 darwin-sandbox, 1 worker.
INFO: Build completed successfully, 9 total actions
```

## With `0.26.0`

```shell
Target //MixedLangFramework:MixedLangFramework up-to-date:
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/MixedLangFramework
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Modules/MixedLangFramework.swiftmodule/x86_64.swiftmodule
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/DemoManager.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/SwiftLibrary.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/MixedLangFramework-umbrella.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Modules/module.modulemap
INFO: Elapsed time: 41.518s, Critical Path: 25.34s
INFO: 147 processes: 13 internal, 132 darwin-sandbox, 1 local, 1 worker.
INFO: Build completed successfully, 147 total actions
```

## Diff

```diff
Target //MixedLangFramework:MixedLangFramework up-to-date:
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/MixedLangFramework
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Modules/MixedLangFramework.swiftmodule/x86_64.swiftmodule
-  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/MixedLangFramework-Swift.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/DemoManager.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/SwiftLibrary.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Headers/MixedLangFramework-umbrella.h
  bazel-out/applebin_ios-ios_x86_64-fastbuild-ST-f35b32a85dd9/bin/MixedLangFramework/MixedLangFramework/MixedLangFramework.framework/Modules/module.modulemap
```
