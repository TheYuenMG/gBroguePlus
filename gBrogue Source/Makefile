LIBTCODDIR=libtcod-1.5.2
SDLDIR=SDL-1.2.14
CFLAGS=$(FLAGS) -I$(LIBTCODDIR)/include -I$(SDLDIR)/include -IgBrogueCode -IPlatformCode -DBROGUE_TCOD -Wall

%.o : %.c
	gcc $(CFLAGS) -O2 -s -o $@ -c $<

OBJS=gBrogueCode/Architect.o \
	gBrogueCode/Combat.o \
	gBrogueCode/Dijkstra.o \
	gBrogueCode/Globals.o \
	gBrogueCode/IO.o \
	gBrogueCode/Buttons.o \
	gBrogueCode/MainMenu.o \
	gBrogueCode/Items.o \
	gBrogueCode/Light.o \
	gBrogueCode/Monsters.o \
	gBrogueCode/Movement.o \
	gBrogueCode/RogueMain.o \
	gBrogueCode/Random.o \
	gBrogueCode/Recordings.o \
	PlatformCode/main.o \
	PlatformCode/platformdependent.o \
	PlatformCode/tcod-platform.o

all : brogue

brogue-icon.o : brogue-icon.ico icon.rc
	windres icon.rc brogue-icon.o

brogue : ${OBJS} brogue-icon.o
	g++ -o brogue.exe ${OBJS} brogue-icon.o -L. -ltcod-mingw -lSDL -L$(LIBTCODDIR)/ -static-libgcc -static-libstdc++ -mwindows
