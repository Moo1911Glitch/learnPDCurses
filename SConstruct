env = Environment()

# env['ENV']['PATH'] = ['E:/Moo/llvm-mingw-20250305-ucrt-x86_64/bin']
env['ENV']['PATH'] = ['E:/Moo/TDMGCC64/bin']
env['BUILDERS']['CustomCC'] = Builder(action='g++ -c -O2 -Wall -I./include -o$TARGET $SOURCE')
env['BUILDERS']['CustomLINK'] = Builder(action='g++ -o$TARGET $SOURCE ./lib/pdcurses.a')

raino = env.CustomCC(['rain.o'], ['rain.c'])
env.Alias('raino', raino)

raine = env.CustomLINK(['rain.exe'], ['rain.o'])
env.Alias('raine', raine)

env.Alias('rain', [raino, raine])

env.Alias('build', ['rain'])
Default('build')
