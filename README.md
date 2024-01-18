# AMX-TMUL-Code-Samples-Intel
Code sample showing Intel® Advanced Matrix Extensions (Intel® AMX) functionality on Intel® Xeon® Scalable processor Max Series and 4th gen Intel® Xeon® Scalable processors.
It is based on https://github.com/intel/AMX-TMUL-Code-Samples
Intel® AMX now introduces new extensions to the x86 Instruction Set Architecture (ISA) to work on matrices and which may accelerate matrix multiplication in AI workloads. It consists of two components:

1. A set of 2-dimensional registers (tiles), which can hold sub-matrices from larger matrices in memory.
2. An accelerator called Tile Matrix Multiply (TMUL) which contains instructions that operate on tiles.

This code sample demonstrates testing the new instructions using intrinsic functions.

A code walk-through for this sample can be found at:
https://www.intel.com/content/www/us/en/developer/articles/code-sample/advanced-matrix-extensions-intrinsics-functions.html


## Purpose

The 2 code sample will multiply matrices A and B of size 16 x 64 containing
- INT8 values, and accumulate the result to a 16 x 16 matrix C containing INT32 values.
- BF16 values, and accumulate the result to a 16 x 16 matrix C containing FP32 values.

This code sample is simplified to highlight use of new Intel(R) AMX instructions. It shows use of instructions to configure the tiles, load data from memory into tiles, perform one matrix multiplication on tiles data and copy the result from tiles to memory. It should not be used as a basis for production code. Only for demostration purposes.

## License

This code sample is licensed under MIT license.  

##  Building the `test-amxtile` executable 

### On a Linux* System
Perform the following steps:
1. Build 

   ```   
    cd src/ 
    make 
    ```

2. Run

    ```
    ./bench-amxtile-BF16.4S.exe  # Should last 4 seconds
    ```

3. Clean 
  
    ```
    make clean  
    ```

## Benchmark scripts
You can find several scripts use to perform different test in the folder [bench_script](bench_script).
Then, you can use python scripts to view the results (see [python](python))