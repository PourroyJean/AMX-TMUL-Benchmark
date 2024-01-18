# Makefile for Compiling Different Executables
# Author: Jean Pourroy, October 2023
# License: MIT

# Compiler and flags
CXX = g++
CXXFLAGS = -g -march=sapphirerapids -O2

# Source file for BF16 benchmarks
SRC_BF16 = bench-amxtile-BF16.c

# Source file for INT8 benchmark
SRC_INT8 = test-amxtile-INT8.c

# Binary names for BF16 benchmarks to be executed in 1, 4 or 40 seconds
BIN_1S = bench-amxtile-BF16.1S.exe
BIN_4S = bench-amxtile-BF16.4S.exe
BIN_40S = bench-amxtile-BF16.40S.exe
BINS_BF16 = $(BIN_1S) $(BIN_4S) $(BIN_40S)

# Binary name for INT8 benchmark
BIN_INT8 = bench-amxtile-INT8.exe

# All binaries
BINS = $(BINS_BF16) $(BIN_INT8)

# Default rule to build all binaries
all: $(BINS)

# Rule for each BF16 binary
$(BIN_1S):
	$(CXX) $(CXXFLAGS) -D NB_OPERATION=100000000 $(SRC_BF16) -o $@

$(BIN_4S):
	$(CXX) $(CXXFLAGS) -D NB_OPERATION=1000000000 $(SRC_BF16) -o $@

$(BIN_40S):
	$(CXX) $(CXXFLAGS) -D NB_OPERATION=10000000000 $(SRC_BF16) -o $@

# Rule for the INT8 binary
$(BIN_INT8):
	$(CXX) $(CXXFLAGS) $(SRC_INT8) -o $@

# Rule to clean generated binaries
clean:
	rm -f $(BINS)
