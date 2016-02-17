BIN = ../bin/
OBJ = ../obj/
SRC = ../src/
INCLUDE = -I../include
CC = gcc
CFLAGS = -c -Wall -g
THRFLAGS = -lpthread

all:$(BIN)http_server $(BIN)http_client $(BIN)index.html

$(BIN)index.html:$(SRC)index.html 
	mv $(SRC)index.html $(BIN).

$(BIN)http_server:$(OBJ)http_server.o
	$(CC) -o http_server $(THRFLAGS) $(OBJ)http_server.o
	mv ./http_server $(BIN)

$(OBJ)http_server.o:$(SRC)http_server.c ../include/header.h
	$(CC) $(CFLAGS) $(SRC)http_server.c  $(INCLUDE)
	mv ./http_server.o $(OBJ)

$(BIN)http_client:$(OBJ)http_client.o
	$(CC) -o http_client $(OBJ)http_client.o
	mv ./http_client $(BIN)

$(OBJ)http_client.o:$(SRC)http_client.c ../include/header.h
	$(CC) $(CFLAGS) $(SRC)http_client.c  $(INCLUDE) 
	mv ./http_client.o $(OBJ)

clean :
	rm $(OBJ)*.o
	rm $(BIN)*
