load("@build_bazel_rules_ios//rules:framework.bzl", "apple_framework")

apple_framework(
    name = "MixedLangFramework",
    srcs = glob(
        [
            "**/*.swift",
            "**/*.m",
            "**/*.h",
        ],
    ),
    public_headers = glob([
        "**/*.h",
    ]),
    module_name = "MixedLangFramework",
    visibility = ["//visibility:public"],
)
