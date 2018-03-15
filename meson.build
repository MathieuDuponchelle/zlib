project('zlib', 'c', version : '1.2.11', license : 'zlib')

pkg = import('pkgconfig')

src = ['adler32.c', 'crc32.c', 'deflate.c', 'infback.c', 'inffast.c', 'inflate.c',
'inftrees.c', 'trees.c', 'zutil.c',
'compress.c', 'uncompr.c', 'gzclose.c', 'gzlib.c', 'gzread.c', 'gzwrite.c']

headers = ['zconf.h', 'zlib.h']

zlib = library('z', src,
  c_args : ['-DZLIB_DLL'],
  install : true,
  version : meson.project_version())

incdir = include_directories('.')

zlib_dep = declare_dependency(link_with : zlib,
  include_directories : incdir)

install_headers(headers)

pkg.generate(name: 'zlib',
             description: 'zlib compression library',
             version: '1.2.11',
             libraries: zlib)
