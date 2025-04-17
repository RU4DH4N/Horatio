project('Horatio', 'cpp', default_options: ['cpp_std=c++20'])

incl = include_directories('include')

buildtype = get_option('buildtype')
message('Building: ' + buildtype)

cpp_args = []
cpp_link_args = []

if buildtype == 'debug'
  cpp_args += ['-ggdb3', '-O0', '-fsanitize=undefined,address']
  cpp_link_args += ['-fsanitize=undefined,address']
elif buildtype == 'release'
  cpp_args += ['-O3', '-march=native', '-flto']
endif

add_project_arguments(cpp_args, language: 'cpp')
add_project_link_arguments(cpp_link_args, language: 'cpp')

sources = files(
  'src/main.cpp'
)

executable('Horatio', sources, include_directories: incl, build_by_default: true)