project(
    'terminal',
    'cpp',
    version: '0.0.1',
    license: 'Apache-2.0',
    meson_version: '>=0.58.1',
)

cc = meson.get_compiler('cpp')


add_project_arguments(
	[
		'-DWLR_USE_UNSTABLE',

		'-Wno-unused-parameter',
		'-Wno-unused-result',
		'-Wno-missing-braces',
		'-Wundef',
		'-Wvla',
	],
	language: 'c',
)

renderer = dependency('renderer')
glfw = cc.find_library('glfw')

terminal_deps = [
    renderer,
    glfw
]

terminal_files = []
terminal_inc = include_directories('include')

subdir('terminal')

