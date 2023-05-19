OBJS=Ch01_01_fcpp.o Ch01_01_fasm.o
CCFLAGS=--std=c++23 -mavx -O3
CC=g++

ch01: Ch01_01_fasm.o Ch01_01_fcpp.o Ch01_01.o
	${CC} ${CCFLAGS} ${OBJS} Ch01_01.o -o ch01 

ch01bm: Ch01_01_fasm.o Ch01_01_fcpp.o Ch01_01_bm.o
	g++ ${CCFLAGS} ${OBJS} Ch01_01_bm.o -lbenchmark -o ch01bm


Ch01_01_fasm.o: Ch01_01_fasm.asm
	uasm -elf64 Ch01_01_fasm.asm

%.o: %.cpp
	${CC} ${CCFLAGS} -c $*.cpp

clean:
	rm -f ch01 ch01bm *.o
