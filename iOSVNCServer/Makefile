CFLAGS = -Wall -std=c99 $(includes)
LDFLAGS = -L /usr/lib/x86_64-linux-gnu -l curl -L /usr/lib/x86_64-linux-gnu -l png -L /usr/lib/x86_64-linux-gnu/ -l vncserver -L /usr/lib/ -l imobiledevice-1.0 -L ./vendor/jsmn -pthread
includes = -I /usr/local/include

iosvncserver: main.o iosscreenshot.o
	$(CC) -o iosvncserver $^ $(LDFLAGS)

dependencies:
	cd ./vendor/jsmn/; make

build: dependencies iosvncserver

clean:
	rm iosvncserver
	rm *.o
	cd ./vendor/jsmn/; make clean
