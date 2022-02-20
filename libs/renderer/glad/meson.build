wget = find_program('wget')

glad_c = 'https://glad.dav1d.de/generated/tmpea6a7ubnglad/src/glad.c'
glad_h = 'https://glad.dav1d.de/generated/tmpea6a7ubnglad/include/glad/glad.h'

outfile_c = 'glad.c'
outfile_h = 'glad.h'

code = custom_target(
    output: outfile_c,
    command: [wget, glad_c, '-O', '@OUTPUT@'],
    install: true,
    install_dir: 'glad'
)

header = custom_target(
    output: outfile_h,
    command: [wget, glad_h, '-O', '@OUTPUT@'],
    install: true,
    install_dir: 'glad'
)

renderer_files += [header, code]
