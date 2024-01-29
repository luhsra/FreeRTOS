project('freertos', 'cpp',
  default_options : ['warning_level=3',
                     'cpp_std=c++17',
                     'buildtype=debugoptimized'])


sources = files(
  'FreeRTOS' / 'Source' / 'croutine.c',
  'FreeRTOS' / 'Source' / 'event_groups.c',
  'FreeRTOS' / 'Source' / 'list.c',
  'FreeRTOS' / 'Source' / 'queue.c',
  'FreeRTOS' / 'Source' / 'stream_buffer.c',
  'FreeRTOS' / 'Source' / 'tasks.c',
  'FreeRTOS' / 'Source' / 'timers.c',
)

here = meson.current_source_dir()

header_dirs = [
  here / 'FreeRTOS' / 'Source' / 'include'
]

toolchains = subproject('toolchains')
arm_enabled = toolchains.get_variable('arm_enabled')

if arm_enabled
  prefix = here / 'FreeRTOS' / 'Source' / 'portable' / 'GCC' / 'ARM_CM3'
  arm_sources = files(prefix / 'port.c')
  arm_header_dirs = [prefix]
endif
