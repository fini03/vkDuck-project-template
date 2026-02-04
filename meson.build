project('vulkan_renderer', 'cpp',
  version : '1.0.0',
  default_options : [
    'cpp_std=c++23',
    'warning_level=0',
    'buildtype=debugoptimized'
  ]
)

# Use vkDuck from Vulkan-Editor (shared library)
vkDuck_proj = subproject('vkDuck')
vkDuck_dep = vkDuck_proj.get_variable('vkDuck_dep')

# Source files (only project-specific generated code)
sources = files(
  'src/main.cpp',
  'generated_files/primitives.cpp'
)

# Include directories
inc_dirs = include_directories('generated_files')

# Compiler arguments
cpp_args = []

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
