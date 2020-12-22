defualt: wacky_static wacky_dynamic

wacky_static: wacky.c libwacky.a
	gcc $^ -o $@

wacky_dynamic: wacky.c libwacky.so
	gcc wacky.c -L. -lwacky -o $@

libwacky.a: wacky_math.o
	ar -rcv $@ $^

libwacky.so: wacky_math.o
	gcc -shared -o libwacky.so wacky_math.o

wacky_math.o: wacky.c wacky_math.h
	gcc -c -fPIC wacky_math.c -o $@

clean:
	rm *.o *.a *.so wacky_static wacky_dynamic