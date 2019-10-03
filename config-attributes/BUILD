# USAGE
## default: bazel build //:hello   --> produces bazel-bin/hello.out
## selecting cpu: bazel build //:hello --cpu=arm
## bazel build //:hello --compilation_mode="dbg"
## another selection:


config_setting(
    name = "config1",
    values = {"cpu": "arm"},
)

config_setting(
    name = "config2",
    values = {"compilation_mode": "dbg"},
)

genrule(
    name = "hello",
    srcs = [],
    outs = ["hello.out"],
    cmd = select({
        "config1": "echo hello from cpu: arm > $@",
        "config2": "echo hello in mode: dbg> $@",
        "//conditions:default": "echo hello in: default > $@",
    }),
)