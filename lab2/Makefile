CC = gcc 
CFLAGS = -Wall -std=gnu99 -g
LD = gcc
LDFLAGS = -std=gnu99 -g 
LDLIBS = -lcurl -lz -pthread

BUILD_DIRECTORY = obj

# Source files
SRCS = $(filter-out test.c, $(wildcard *.c))

# Object files
OBJS = $(addprefix $(BUILD_DIRECTORY)/, $(SRCS:.c=.o))

# All targets
TARGETS = paster

# Target: all
all: paster

# Target: paster
paster : $(OBJS)
	$(LD) -o $@ $^ $(LDLIBS) $(CFLAGS)

# Target: clean
clean:
	rm -rf paster $(OBJS) $(TARGETS) $(BUILD_DIRECTORY)

# Pattern rule for object files
$(BUILD_DIRECTORY)/%.o: %.c | obj
	$(CC) $(CFLAGS) -c $< -o $@

# Create obj directory if it doesn't exist
obj:
	mkdir -p $(BUILD_DIRECTORY)

.PHONY: clean all