all_sources += files(
  'SDL_haptic.c',
)
if host_machine.system() == 'linux'
  subdir('linux')
elif host_machine.system() == 'windows'
  subdir('windows')
else
  subdir('dummy')
endif
