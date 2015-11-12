all_sources += files(
  'SDL_power.c',
)

if host_machine.system() == 'linux'
  subdir('linux')
elif host_machine.system() == 'windows'
  subdir('windows')
else
  error('Unsupported platform.')
endif
