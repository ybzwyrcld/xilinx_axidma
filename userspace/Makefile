.PHONY: clean
CROSS_COMPILE=arm-xilinx-linux-gnueabi-
CC=$(CROSS_COMPILE)gcc
CPP=$(CROSS_COMPILE)g++
CFLAGS = -O

all: axidma_transfer axidma_transfer_twoway

util.o : util.c
	$(CC) -c $<

libaxidma.o : libaxidma.c
	$(CC) -c $<

axidma_transfer.o : axidma_transfer.c
	$(CC) -c $<

axidma_transfer_twoway.o : axidma_transfer_twoway.c
	$(CC) -c $<

axidma_transfer : axidma_transfer.o util.o libaxidma.o
	$(CC) $(CFLAGS) -o axidma_transfer $^

axidma_transfer_twoway : axidma_transfer_twoway.o util.o libaxidma.o
	$(CC) $(CFLAGS) -o axidma_transfer_twoway $^

clean:
	rm -f *.o axidma_transfer axidma_transfer_twoway

