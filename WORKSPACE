workspace(name = "com_github_tmc_rules_helm")

load(":repos.bzl", "helm_repositories")
helm_repositories()

local_repository(
    name = "com_github_yujunz_rules_helm_external",
    path = "../rules_helm_external"
)
load(
  "@com_github_yujunz_rules_helm_external//helm:deps.bzl",
  "helm_register_toolchains",
  "helm_rules_dependencies",
)
helm_rules_dependencies()
helm_register_toolchains()

load("//tools:buildifier.bzl", "buildifier_repositories")
buildifier_repositories()

# Start stardoc rules
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
git_repository(
    name = "io_bazel_skydoc",
    remote = "https://github.com/bazelbuild/skydoc.git",
    tag = "0.3.0",
)
load("@io_bazel_skydoc//:setup.bzl", "skydoc_repositories")
skydoc_repositories()
load("@io_bazel_rules_sass//:package.bzl", "rules_sass_dependencies")
rules_sass_dependencies()
load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories")
node_repositories()
load("@io_bazel_rules_sass//:defs.bzl", "sass_repositories")
sass_repositories()
# End stardoc rules
