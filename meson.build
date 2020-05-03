project('hidviz', 'cpp', version: '0.1.5', license: 'GPLv3.0+', default_options: 'cpp_std=c++14')

libhidx = subproject('libhidx')

libhidx_dep = libhidx.get_variable('libhidx_dep')
libhidx_server_dep = libhidx.get_variable('libhidx_server_dep')
buffer_gen_dep = libhidx.get_variable('buffer_gen_dep')
protobuf_dep = libhidx.get_variable('protobuf_dep')

# the original has this but it produces a warning on meson
#if ['gcc', 'clang'].contains(cxx.get_id())
#   add_project_arguments('-Wall', '-Wextra', language: 'cpp')
#endif

subdir('hidviz')
