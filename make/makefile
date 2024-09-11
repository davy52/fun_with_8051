
ROOT_PATH=../

BUILD_PATH=$(ROOT_PATH)/build/

OBJ_PATH=$(BUILD_PATH)/objects/

SRC_ROOT_PATH=$(ROOT_PATH)/src/



INCLUDE=$(SRC_ROOT_PATH)/math/

IFLAGS=$(foreach inc, $(INCLUDE), -I$(inc) )

CFLAGS=-mmcs51

all: dirs compile link

dirs:
	mkdir -p $(BUILD_PATH)
	mkdir -p $(OBJ_PATH)

compile:
	sdcc $(IFLAGS) -c $(SRC_ROOT_PATH)/main/main.c -o $(OBJ_PATH)
	sdcc $(IFLAGS) -c $(SRC_ROOT_PATH)/math/math.c -o $(OBJ_PATH)
	#not proud of this one

link:
	sdcc $(IFLAGS) $(OBJ_PATH)/main.rel $(OBJ_PATH)/math.rel -o $(BUILD_PATH)

.PHONY: clean

clean:
	$(RM)  $(OBJ_PATH)/*
	$(RM)  $(BUILD_PATH)/*
