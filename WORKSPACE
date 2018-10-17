# Load in rules_go.
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "7519e9e1c716ae3c05bd2d984a42c3b02e690c5df728dc0a84b23f90c355c5a1",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/0.15.4/rules_go-0.15.4.tar.gz"],
)

load("@io_bazel_rules_go//go:def.bzl", "go_rules_dependencies", "go_register_toolchains")

go_rules_dependencies()

go_register_toolchains()

# Depend on buildtools.
http_archive(
    name = "bazel_gazelle",
    sha256 = "c0a5739d12c6d05b6c1ad56f2200cb0b57c5a70e03ebd2f7b87ce88cabf09c7b",
    urls = ["https://github.com/bazelbuild/bazel-gazelle/releases/download/0.14.0/bazel-gazelle-0.14.0.tar.gz"],
)

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")

gazelle_dependencies()

load("@bazel_gazelle//:deps.bzl", "go_repository")

go_repository(
    name = "com_github_bazelbuild_buildtools",
    commit = "90fd34a8dffeb3b823c4ddefad93cc67d099e738",
    importpath = "github.com/bazelbuild/buildtools",
)

# used for build.proto
http_archive(
    name = "io_bazel",
    sha256 = "66135f877d0cc075b683474c50b1f7c3e2749bf0a40e446f20392f44494fefff",
    strip_prefix = "bazel-0.12.0",
    urls = [
        "http://mirror.bazel.build/github.com/bazelbuild/bazel/archive/0.12.0.tar.gz",
        "https://github.com/bazelbuild/bazel/archive/0.12.0.tar.gz",
    ],
)
