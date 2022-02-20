project(
	'angel',
	'c',
	version: '0.0.1',
	license: 'Apache-2.0',
	meson_version: '>=0.58.1',
	default_options: [
		'c_std=c11',
		'warning_level=2',
        'werror=true',
	],
)

soversion = 0

cc = meson.get_compiler('c')

add_project_arguments(cc.get_supported_arguments([
	'-Wundef',
	'-Wlogical-op',
	'-Wmissing-include-dirs',
	'-Wold-style-definition',
	'-Wpointer-arith',
	'-Winit-self',
	'-Wimplicit-fallthrough=2',
	'-Wendif-labels',
	'-Wstrict-aliasing=2',
	'-Woverflow',
	'-Walloca',
	'-Wno-missing-braces',
	'-Wno-missing-field-initializers',
	'-Wno-unused-parameter',
]), language: 'c')

math = cc.find_library('m')

renderer_files = []

subdir('renderer')
subdir('include')

renderer_deps = [
	math,
]

renderer_inc = include_directories('include')

librenderer = library(
	meson.project_name(), renderer_files,
	soversion: soversion,
	dependencies: renderer_deps,
	include_directories: [renderer_inc],
	install: true,
)

pkgconfig = import('pkgconfig')
pkgconfig.generate(librenderer,
	version: meson.project_version(),
	filebase: meson.project_name(),
	name: meson.project_name(),
	description: 'Modern rendering system for the Maren desktop enviroment',
)


