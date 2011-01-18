CFLAGS=-Wall -Werror -Iinclude -g3 -ggdb3
LDFLAGS=-lev -lpthread
CC=gcc ${CFLAGS} ${LDFLAGS}

all: clean server remote test

server:
	$(CC) -o dummyd dummy-daemon.c dummy-worker.c dummy-worker-thread.c dummy_settings.c rand.c

remote:
	$(CC) -o dummy-rc dummy-rc.c dummy_settings.c -Iinclude -lev

test:
	$(CC) -o rand-test rand.c rand-test.c -Iinclude
	$(CC) -o dummy-worker-test dummy-worker-test.c dummy-worker.c rand.c -Iinclude

clean:
	@rm dummyd dummy-rc rand-test dummy-worker-test -rf