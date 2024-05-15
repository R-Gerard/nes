CFLAGS += -Wall -Wextra
CFLAGS += $(shell pkg-config --cflags libpng)
CXXFLAGS += -Wall -Wextra
CXXFLAGS += $(shell pkg-config --cflags libpng)
CXXFLAGS += -fno-exceptions -fno-rtti
#LDFLAGS += -Wl,-as-needed -Wl,-O1
LDFLAGS += $(shell pkg-config --libs libpng)

.phony: all clean
all: png2chr chr2png sametiles tilecoords nes2hex pngreorder png2gba \
	palstat coord2metasprite nesasmc nsf2data text2data \
	coord2lz4

png2chr: png2chr.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(PNG_CFLAGS) $(LDFLAGS)

png2gba: png2gba.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

chr2png: chr2png.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

sametiles: sametiles.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

tilecoords: tilecoords.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

nes2hex: nes2hex.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

pngreorder: pngreorder.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

palstat: palstat.o common.o
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)

coord2metasprite: coord2metasprite.o common.o

nesasmc: nesasmc.o
	$(CXX) -o $@ $^ $(CXXFLAGS)

nsf2data: nsf2data.o
	$(CXX) -o $@ $^ $(CXXFLAGS)

text2data: text2data.o
	$(CXX) -o $@ $^ $(CXXFLAGS)

coord2lz4: coord2lz4.o common.o lz4hc.o lz4.o

clean:
	rm -f *.o png2chr chr2png sametiles tilecoords nes2hex pngreorder png2gba palstat \
		coord2metasprite nesasmc nsf2data text2data coord2lz4
