workspace(name = "angular_material_src")

# Add nodejs rules
git_repository(
  name = "build_bazel_rules_nodejs",
  remote = "https://github.com/bazelbuild/rules_nodejs.git",
  commit = "0.3.1",
)

git_repository(
    name = "io_bazel_rules_closure",
    remote = "https://github.com/bazelbuild/rules_closure.git",
    commit = "172f84fe96e07214fa7337b081648d4a61b45b93",
)

# NOTE: this rule installs nodejs, npm, and yarn, but does NOT install
# your npm dependencies. You must still run the package manager.
load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories")
node_repositories(package_json = ["//:package.json"])

# Add sass rules
git_repository(
  name = "io_bazel_rules_sass",
  remote = "https://github.com/bazelbuild/rules_sass.git",
  tag = "0.0.3",
)

load("@io_bazel_rules_sass//sass:sass.bzl", "sass_repositories")
sass_repositories()

# Add TypeScript rules

#git_repository(
local_repository(
    name = "build_bazel_rules_typescript",
    #remote = "https://github.com/adamyi/rules_typescript.git",
    #commit = "3147f802ea726a9fedf02b97cf3640b5497be519",
    path = "../rules_typescript"
)

# Setup TypeScript Bazel workspace
load("@build_bazel_rules_typescript//:defs.bzl", "ts_setup_workspace")
ts_setup_workspace()

# Add Angular rules
# git_repository(
local_repository(
    name = "angular",
    # remote = "https://github.com/angular/bazel-builds",
    # commit = "5b0e7822a4dcc92ec2db7b0dc74236b8ff5f3e49",
    path = "../bazel-builds",
)

# Add rxjs
local_repository(
  name = "rxjs",
  path = "node_modules/rxjs/src",
)
