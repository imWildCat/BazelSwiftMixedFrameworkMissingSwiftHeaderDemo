workspace(name = "BazelSwiftMixedFrameworkMissingSwiftHeaderDemo")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_SWIFT_VERSION = "0.26.0"
# RULES_SWIFT_VERSION = '0.24.0' # Use `0.24.0` can fix this bug

http_archive(
    name = "build_bazel_rules_swift",
    url = "https://github.com/bazelbuild/rules_swift/releases/download/%s/rules_swift.%s.tar.gz" % (RULES_SWIFT_VERSION, RULES_SWIFT_VERSION),
)

git_repository(
    name = "build_bazel_rules_apple",
    branch = "master",
    remote = "https://github.com/bazelbuild/rules_apple.git",
)

load(
    "@build_bazel_rules_apple//apple:repositories.bzl",
    "apple_rules_dependencies",
)

apple_rules_dependencies()

load(
    "@build_bazel_rules_swift//swift:repositories.bzl",
    "swift_rules_dependencies",
)

swift_rules_dependencies()

load(
    "@build_bazel_rules_swift//swift:extras.bzl",
    "swift_rules_extra_dependencies",
)

swift_rules_extra_dependencies()

git_repository(
    name = "build_bazel_apple_support",
    remote = "https://github.com/bazelbuild/apple_support.git",
    tag = "0.13.0",
)

git_repository(
    name = "bazel_skylib",
    remote = "https://github.com/bazelbuild/bazel-skylib.git",
    tag = "1.2.1",
)

git_repository(
    name = "build_bazel_rules_ios",
    branch = "master",
    remote = "https://github.com/bazel-ios/rules_ios.git",
)

load(
    "@build_bazel_rules_ios//rules:repositories.bzl",
    "rules_ios_dependencies",
)

rules_ios_dependencies()
