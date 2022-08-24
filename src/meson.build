pkgdatadir = join_paths(get_option('prefix'), get_option('datadir'), meson.project_name())
moduledir = join_paths(pkgdatadir, meson.project_name())

conf = configuration_data()
conf.set('LUA', find_program('lua').full_path())
conf.set('VERSION', meson.project_version())
conf.set('NAME', meson.project_name())
conf.set('libdir', join_paths(get_option('prefix'), get_option('libdir')))
conf.set('datadir', join_paths(get_option('prefix'), get_option('datadir')))
conf.set('localedir', join_paths(get_option('prefix'), get_option('localedir')))
conf.set('pkgdatadir', pkgdatadir)
conf.set('moduledir', moduledir)

configure_file(
  input: 'iup_example.in',
  output: meson.project_name(),
  configuration: conf,
  install: true,
  install_dir: get_option('bindir')
)

example_sources = [
  'init.lua',
]

install_data(example_sources, install_dir: moduledir)
