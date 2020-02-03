calc.o: calc.c calc.h
	gcc -g -Wall -c calc.c -o calc.o
calcula: calcula.c calc.o
	gcc -Wall -g calc.c -o calcula
.PHONY: clean
clean:
	rm -rf *.o
	rm calcula
.PHONY: dist
dist: clean calcula
	rm -rf ../dist;
	mkdir -p ../dist/usr/bin/calc
	cp calcula ../dist/usr/bin/calc
.PHONY: targz
targz: clean
	mkdir -p source
	cp *.c *.h Makefile source
	tar -cvf calcula.tar source
	gzip calcula.tar
	rm -rf calcula.tar
	rm -rf source
install: dist
	sudo cp -r ../dist/* /
