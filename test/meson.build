test('testfile', executable('testfile', 'testfile.c', dependencies : sdl2_dep))

if gl_dep.found()
  executable('testgl2', 'testgl2.c',
  c_args : ['-DHAVE_OPENGL=1'],
  dependencies : sdl2_dep)
endif
