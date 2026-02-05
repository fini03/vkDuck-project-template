# Third-Party Licenses

## Dependencies Used in This Project Template

These are fetched via Meson wrap files when building:

| Project | License | Wrap File |
|---------|---------|-----------|
| [glm](https://github.com/g-truc/glm) | MIT | `glm.wrap` |
| [SDL3](https://github.com/libsdl-org/SDL) | zlib | `sdl3.wrap` |
| [Vulkan Memory Allocator](https://github.com/GPUOpen-LibrariesAndSDKs/VulkanMemoryAllocator) | MIT | `vulkan-memory-allocator.wrap` |

## Dependencies Bundled in vkDuck

The pre-compiled `vkDuck` library (in `lib/`) includes the following third-party dependencies. These are **not** part of this template repository but are linked into vkDuck:

| Project | License | License File |
|---------|---------|--------------|
| [imgui](https://github.com/ocornut/imgui) | MIT | (in vkDuck) |
| [imgui-node-editor](https://github.com/thedmd/imgui-node-editor) | MIT | `imgui-node-editor-LICENSE` |
| [nlohmann-json](https://github.com/nlohmann/json) | MIT | `nlohmann-json-LICENSE` |
| [shader-slang](https://github.com/shader-slang/slang) | MIT | (in vkDuck) |
| [tinyfiledialogs](https://sourceforge.net/projects/tinyfiledialogs/) | zlib | `tinyfiledialogs-LICENSE` |
| [tinygltf](https://github.com/syoyo/tinygltf) | MIT | `tinygltf-LICENSE` |
| [wuffs](https://github.com/nicholasbishop/wuffs-rs) | Apache-2.0 | `wuffs-LICENSE` |

## vkDuck License

The vkDuck library itself is licensed under MIT. See `vkDuck-LICENSE`.