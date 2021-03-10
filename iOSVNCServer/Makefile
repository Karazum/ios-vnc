CFLAGS = -Wall -std=c99 $(includes)
LDFLAGS = -L /usr/local/opt/ -L ./vendor/jsmn/
LDLIBS = -l imobiledevice-1.0 -l png -l vncserver -l curl
includes = -I /usr/local/include

iosvncserver: main.o iosscreenshot.o
	$(CC) $(LDFLAGS) $(LDLIBS) -o iosvncserver $^ 

dependencies: 
	cd ./vendor/jsmn/; make

build: dependencies iosvncserver

clean:
	rm iosvncserver
	rm *.o
	cd ./vendor/jsmn/; make clean
