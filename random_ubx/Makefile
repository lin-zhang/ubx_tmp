ROOT_DIR=$(CURDIR)/../..
include $(ROOT_DIR)/make.conf
INCLUDE_DIR=$(ROOT_DIR)/src/

TYPES:=$(wildcard types/*.h)
HEXARRS:=$(TYPES:%=%.hexarr)

random_ubx.so: random_ubx.o $(INCLUDE_DIR)/libubx.so 
	${CC} $(CFLAGS_SHARED) -o random_ubx.so random_ubx.o $(INCLUDE_DIR)/libubx.so

random_ubx.o: random_ubx.c $(INCLUDE_DIR)/ubx.h $(INCLUDE_DIR)/ubx_types.h $(INCLUDE_DIR)/ubx.c $(HEXARRS)
	${CC} -fPIC -I$(INCLUDE_DIR) -c $(CFLAGS) random_ubx.c

clean:
	rm -f *.o *.so *~ core $(HEXARRS)
