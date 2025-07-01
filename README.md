# ZGLFW - A GLFW library binding written in Zig

This is a fork from unmaintained GLFW binding repository [Mach engine](https://github.com/hexops/mach) was using. It contains Ziggified GLFW bindings with 100% API coverage, zero-fuss installation, cross compilation, and more.

For an example of how to use this library, check out the [coderloff/zglfw-example](https://github.com/coderloff/zglfw-example)

For a packaged GLFW library, check out [coderloff/zig-glfw](https://github.com/coderloff/zig-glfw).

## Adding to your project

To add this library to your Zig project, first fetch the repository to add the dependency to `build.zig.zon`:
```bash
zig fetch --save https://github.com/coderloff/zig-glfw/archive/[latest-commit-hash].zip
```

Latest commit hash can be acquired by entering `Commits` tab on the repository and pressing the `Copy full SHA` button next to the latest commit.

Then, add the dependency to your `build.zig` file:
```zig
...

const glfw_dep = b.dependency("zglfw", .{
    .target = target,
    .optimize = optimize,
});

exe.root_module.addImport("zglfw", glfw_dep.module("zglfw"));

...
```