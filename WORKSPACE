load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_tweag_rules_nixpkgs",
    sha256 = "e40d2067638e846bf05164296bcad83b68462cbe24cda7419bdce46c9af106fd",
    strip_prefix = "rules_nixpkgs-8e0e3848cf9a4125b3628f8d09dafc00a84f5358",
    urls =
        ["https://github.com/tweag/rules_nixpkgs/archive/8e0e3848cf9a4125b3628f8d09dafc00a84f5358.tar.gz"],
)

load("@io_tweag_rules_nixpkgs//nixpkgs:repositories.bzl", "rules_nixpkgs_dependencies")

rules_nixpkgs_dependencies()

load("@io_tweag_rules_nixpkgs//nixpkgs:nixpkgs.bzl", "nixpkgs_cc_configure", "nixpkgs_git_repository", "nixpkgs_package")

nixpkgs_git_repository(
    name = "nixpkgs",
    revision = "20.03",  # Any tag or commit hash
    sha256 = "f21ca8bc4c8f848a351232e09f3a58d280c05323173a78a5a6013937fb05c6fe",  # optional sha to verify package integrity!
)

nixpkgs_cc_configure(repositories = {"nixpkgs": "@nixpkgs//:default.nix"})
