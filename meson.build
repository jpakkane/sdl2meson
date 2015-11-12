project('sdl2', 'c', version : '2.0.3',
  default_options: ['c_std=gnu99'])

varr = meson.project_version().split('.')
version_major = varr[0]
version_minor = varr[1]
version_micro = varr[2]

cc = meson.get_compiler('c')
cdata = configuration_data()
check_headers = [
  ['HAVE_ALLOCA_H', 'alloca.h'],
  ['HAVE_SYS_TYPES_H', 'sys/types.h'],
  ['HAVE_STDIO_H', 'stdio.h'],
  ['HAVE_STDLIB_H', 'stdlib.h'],
  ['HAVE_STDARG_H', 'stdarg.h'],
  ['HAVE_MALLOC_H', 'malloc.h'],
  ['HAVE_MEMORY_H', 'memory.h'],
  ['HAVE_STRING_H', 'string.h'],
  ['HAVE_STRINGS_H', 'strings.h'],
  ['HAVE_INTTYPES_H', 'inttypes.h'],
  ['HAVE_STDINT_H', 'stdint.h'],
  ['HAVE_CTYPE_H', 'ctype.h'],
  ['HAVE_MATH_H', 'math.h'],
  ['HAVE_ICONV_H', 'iconv.h'],
  ['HAVE_SIGNAL_H', 'signal.h'],
  ['HAVE_ALTIVEC_H', 'altivec.h'],
  ['HAVE_PTHREAD_NP_H', 'pthread/np.h'],
  ['HAVE_LIBUDEV_H', 'libudev.h'],
  ['HAVE_DBUS_DBUS_H', 'dbus/dbus.h'],
  ['HAVE_STDARG_H', 'stdarg.h'],
  ['HAVE_STDDEF_H', 'stddef.h'],
]

foreach h : check_headers
  if cc.has_header(h.get(1))
    cdata.set(h.get(0), 1)
  endif
endforeach

check_functions = [
  ['HAVE_MALLOC', 'malloc', '#include<stdlib.h>'],
  ['HAVE_CALLOC', 'calloc', '#include<stdlib.h>'],
  ['HAVE_REALLOC', 'realloc', '#include<stdlib.h>'],
  ['HAVE_FREE', 'free', '#include<stdlib.h>'],
  ['HAVE_ALLOCA', 'alloca', '#include<alloca.h>'],
  ['HAVE_GETENV', 'setenv', '#include<stdlib.h>'],
  ['HAVE_SETENV', 'setenv', '#include<stdlib.h>'],
  ['HAVE_PUTENV', 'putenv', '#include<stdlib.h>'],
  ['HAVE_UNSETENV', 'unsetenv', '#include<stdlib.h>'],
  ['HAVE_QSORT', 'qsort', '#include<stdlib.h>'],
  ['HAVE_ABS', 'abs', '#include<stdlib.h>'],
  ['HAVE_BCOPY', 'bcopy', '#include<strings.h>'],
  ['HAVE_MEMSET', 'memset', '#include<string.h>'],
  ['HAVE_MEMCPY', 'memcpy', '#include<string.h>'],
  ['HAVE_MEMMOVE', 'memmove', '#include<string.h>'],
  ['HAVE_MEMCMP', 'memcmp', '#include<string.h>'],
  ['HAVE_STRLEN', 'strlen', '#include<string.h>'],
  ['HAVE_STRLCPY', 'strlcpy', '#include<string.h>'],
  ['HAVE_STRLCAT', 'strlcat', '#include<string.h>'],
  ['HAVE_STRDUP', 'strdup', '#include<string.h>'],
  ['HAVE__STRREV', '_strrev', '#include<string.h>'],
  ['HAVE__STRUPR', '_strupr', '#include<string.h>'],
  ['HAVE__STRLWR', '_strlwr', '#include<string.h>'],
  ['HAVE_INDEX', 'index', '#include<strings.h>'],
  ['HAVE_RINDEX', 'rindex', '#include<strings.h>'],
  ['HAVE_STRCHR', 'strchr', '#include<string.h>'],
  ['HAVE_STRRCHR', 'strrchr', '#include<string.h>'],
  ['HAVE_STRSTR', 'strstr', '#include<string.h>'],
# check token HAVE_ITOA
# check token HAVE__LTOA
# check token HAVE__UITOA
# check token HAVE__ULTOA
  ['HAVE_STRTOL', 'strtol', '#include<stdlib.h>'],
  ['HAVE_STRTOUL', 'strtoul', '#include<stdlib.h>'],
# check token HAVE__I64TOA
# check token HAVE__UI64TOA
  ['HAVE_STRTOLL', 'strtoll', '#include<stdlib.h>'],
  ['HAVE_STRTOULL', 'strtoull', '#include<stdlib.h>'],
  ['HAVE_STRTOD', 'strtod', '#include<stdlib.h>'],
  ['HAVE_ATOI', 'atoi', '#include<stdlib.h>'],
  ['HAVE_ATOF', 'atof', '#include<stdlib.h>'],
  ['HAVE_STRCMP', 'strcmp', '#include<string.h>'],
  ['HAVE_STRNCMP', 'strncmp', '#include<string.h>'],
# check token HAVE__STRICMP
  ['HAVE_STRCASECMP', 'strcasecmp', '#include<strings.h>'],
# check token HAVE__STRNICMP
  ['HAVE_STRNCASECMP', 'strncasecmp', '#include<strings.h>'],
  ['HAVE_VSSCANF', 'vsscanf', '#include<stdio.h>'],
  ['HAVE_VSNPRINTF', 'vsnprintf', '#include<stdio.h>'],
  ['HAVE_ATAN', 'atan', '#include<math.h>'],
  ['HAVE_ATAN2', 'atan2', '#include<math.h>'],
  ['HAVE_ACOS', 'acos', '#include<math.h>'],
  ['HAVE_ASIN', 'asin', '#include<math.h>'],
  ['HAVE_CEIL', 'ceil', '#include<math.h>'],
  ['HAVE_COPYSIGN', 'copysign', '#include<math.h>'],
  ['HAVE_COS', 'cos', '#include<math.h>'],
  ['HAVE_COSF', 'cosf', '#include<math.h>'],
  ['HAVE_FABS', 'fabs', '#include<math.h>'],
  ['HAVE_FLOOR', 'floor', '#include<math.h>'],
  ['HAVE_LOG', 'log', '#include<math.h>'],
  ['HAVE_POW', 'pow', '#include<math.h>'],
  ['HAVE_SCALBN', 'scalbn', '#include<math.h>'],
  ['HAVE_SIN', 'sin', '#include<math.h>'],
  ['HAVE_SINF', 'sinf', '#include<math.h>'],
  ['HAVE_SQRT', 'sqrt', '#include<math.h>'],
  ['HAVE_FSEEKO', 'fseeko', '#include<stdio.h>'],
  ['HAVE_FSEEKO64', 'fseeko64', '#include<stdio.h>'],
  ['HAVE_SIGACTION', 'sigaction', '#include<signal.h>'],
# check token HAVE_SA_SIGACTION
  ['HAVE_SETJMP', 'setjmp', '#include<setjmp.h>'],
  ['HAVE_NANOSLEEP', 'nanosleep', '#include<time.h>'],
  ['HAVE_SYSCONF', 'sysconf', '#include<unistd.h>'],
  ['HAVE_SYSCTLBYNAME', 'sysctlbyname', '#include<sys/sysctl.h>'],
  ['HAVE_CLOCK_GETTIME', 'clock_gettime', '#include<time.h>'],
  ['HAVE_GETPAGESIZE', 'getpagesize', '#include<unistd.h>'],
  ['HAVE_MPROTECT', 'mprotect', '#include<sys/mman.h>'],
# check token HAVE_ICONV
  ['HAVE_PTHREAD_SETNAME_NP', 'pthread_setname_np', '#include<pthread.h>'],
  ['HAVE_PTHREAD_SET_NAME_NP', 'pthread_set_name_np', '#include<pthread.h>'],
# check token HAVE_SEM_TIMEDWAIT
]

foreach f : check_functions
  if cc.has_function(f.get(1), prefix : f.get(2))
    cdata.set(f.get(0), 1)
  endif
endforeach

cdata.set('HAVE_LIBC', 1)
cdata.set('HAVE_M_PI', 1)
cdata.set('HAVE_GCC_ATOMICS', 1)
cdata.set('HAVE_GCC_SYNC_LOCK_TEST_AND_SET', 1)
cdata.set('HAVE_PTHREAD_SPINLOCK', 1)
cdata.set('SDL_POWER_LINUX', 1)
cdata.set('SDL_THREAD_PTHREAD', 1)
cdata.set('SDL_JOYSTICK_LINUX', 1)
cdata.set('SDL_INPUT_LINUXEV', 1)
cdata.set('SDL_HAPTIC_LINUX', 1)
cdata.set('SDL_TIMER_UNIX', 1)
cdata.set('SDL_FILESYSTEM_UNIX', 1)
cdata.set('SDL_DYNAMIC_API', 1)
cdata.set('SDL_LOADSO_DLOPEN', 1)
cdata.set('SDL_VIDEO_DRIVER_X11', 1)
cdata.set('SDL_VIDEO_DRIVER_X11_DYNAMIC_XINPUT2', 1)
cdata.set('SDL_VIDEO_DRIVER_X11_XINPUT2', 1)
cdata.set('SDL_VIDEO_DRIVER_X11_XINPUT2_SUPPORTS_MULTITOUCH', 1)
cdata.set('SDL_VIDEO_DRIVER_X11_SUPPORTS_GENERIC_EVENTS', 1)

core_inc = include_directories('.', 'include')
all_sources = []

x11_dep = dependency('x11', required : false)
xi_dep = dependency('xi', required : false)
gl_dep = dependency('gl', required : false)
xrandr_dep = dependency('xrandr', required : false)
xinerama_dep = dependency('xinerama', required : false)

if x11_dep.found()
  if gl_dep.found()
    cdata.set('SDL_VIDEO_OPENGL_GLX', 1)
  endif
  if xrandr_dep.found()
    cdata.set('SDL_VIDEO_DRIVER_X11_DYNAMIC_XRANDR', 1)
    cdata.set('SDL_VIDEO_DRIVER_X11_XRANDR', 1)
  endif
  if xinerama_dep.found()
    cdata.set('SDL_VIDEO_DRIVER_X11_XINERAMA', 1)
    cdata.set('SDL_VIDEO_DRIVER_X11_DYNAMIC_XINERAMA', 1)
  endif
endif

# The config file is at root because we want to
# ensure that it comes before the include subdir
# in search order and include also has a SDL_config.h.
configure_file(input : 'SDL_config.h.meson',
  output : 'SDL_config.h',
  configuration : cdata)


subdir('src')
core_args = ['-pthread']
core_deps = [find_library('m', required : false),
  find_library('dl', required : false),
  find_library('pthread', required : false),
  x11_dep, xi_dep, xrandr_dep, gl_dep, xinerama_dep,
]

sdl2 = library('sdl2',
  all_sources,
  include_directories : core_inc,
  c_args : core_args,
  dependencies : core_deps,
)
sdl2_dep = declare_dependency(link_with : sdl2,
  include_directories : core_inc)

subdir('test')