project('vulkan_renderer', 'cpp',
  version : '1.0.0',
  default_options : [
    'cpp_std=c++23',
    'warning_level=0',
    'buildtype=debugoptimized'
  ]
)

# Dependencies (via Meson wraps)
vulkan_dep = dependency('vulkan')
sdl3_dep = dependency('sdl3')
glm_dep = dependency('glm')
vma_dep = dependency('vulkan-memory-allocator', include_type: 'system')

# Pre-compiled vkDuck library (built with Vulkan-Editor)
vkDuck_inc = include_directories('include')
cpp = meson.get_compiler('cpp')
vkDuck_lib = cpp.find_library('vkDuck',
  dirs: meson.current_source_dir() / 'lib',
  static: true
)

# Combine vkDuck with its dependencies
vkDuck_dep = declare_dependency(
  include_directories: vkDuck_inc,
  dependencies: [vkDuck_lib, vulkan_dep, sdl3_dep, glm_dep, vma_dep]
)

# Source files (project-specific generated code)
sources = files(
  'src/main.cpp',
  'generated_files/primitives.cpp',
  'generated_files/camera_instances.cpp'
)

# Include directories
inc_dirs = include_directories('generated_files')

# Compiler arguments
cpp_args = ['-DVKDUCK_NO_VMA_IMPLEMENTATION']

if host_machine.system() == 'darwin'
  cpp_args += ['-DVK_USE_PLATFORM_MACOS_MVK']
elif host_machine.system() == 'linux'
  cpp_args += ['-DVK_USE_PLATFORM_XCB_KHR']
elif host_machine.system() == 'windows'
  cpp_args += ['-DVK_USE_PLATFORM_WIN32_KHR']
endif

# Build executable
executable('main',
  sources,
  include_directories : [inc_dirs],
  dependencies : [vkDuck_dep],
  cpp_args : cpp_args,
  install : true
)
