load("//tools:defs.bzl", "go_library")
load("//test/benchmarks:defs.bzl", "benchmark_test")

package(licenses = ["notice"])

go_library(
    name = "database",
    testonly = 1,
    srcs = ["database.go"],
    deps = ["//test/benchmarks/harness"],
)

benchmark_test(
    name = "database_test",
    size = "enormous",
    srcs = ["redis_test.go"],
    library = ":database",
    visibility = ["//:sandbox"],
    deps = [
        "//pkg/test/dockerutil",
        "//test/benchmarks/harness",
        "//test/benchmarks/tools",
    ],
)
