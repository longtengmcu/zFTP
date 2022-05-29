# RT-Thread building script for component

from building import *

cwd = GetCurrentDir()
src = Glob('src/*.c') + Glob('src/*.cpp')
CPPPATH = [cwd + '/inc']

if GetDepend(['ZFTP_USING_SAMPLE']):
    src += Glob('samples/*.c')

group = DefineGroup('zFTP', src, depend = ['PKG_USING_ZFTP'], CPPPATH = CPPPATH)

Return('group')
