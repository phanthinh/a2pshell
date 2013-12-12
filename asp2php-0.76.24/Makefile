
CC=gcc
LD=ld
CFLAGS=-Wall

default:
	cd src && make
	@if [ -e src/asp2php.exe ]; then mv src/asp2php.exe asp2php.exe; fi;
	@if [ -e src/asp2php ]; then mv src/asp2php asp2php; fi;
	@if [ -e asp2php.exe ]; then strip asp2php.exe; fi;
	@if [ -e asp2php ]; then strip asp2php; fi;

clean:
	cd src && make clean
	@if [ -e asp2php ]; then rm asp2php; fi;
	@if [ -e gtkasp2php ]; then rm gtkasp2php; fi;

gui:
	cd src && make gui
	@mv src/gtkasp2php .

install:
	@if [ -e asp2php ]; then install asp2php /usr/local/bin; fi;
	@if [ -e gtkasp2php ]; then install gtkasp2php /usr/local/bin; fi;
	@echo "Compiled programs have been installed in /usr/local/bin"
	@echo ""

uninstall:
	@if [ -e /usr/local/bin/asp2php ]; then rm /usr/local/bin/asp2php; fi;
	@if [ -e /usr/local/bin/gtkasp2php ]; then rm /usr/local/bin/gtkasp2php; fi;
	@echo "asp2php has been uninstalled."
	@echo ""

all: default

solaris:
	pkgmk -d /tmp
	pkgtrans -s /tmp asp2php-0.76.15-sol9-sparc-local KOHNasp2


