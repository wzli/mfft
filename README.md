# mFFT 
A minimalist and portable Fast Fourier Transform library for small applications.
- Contains forward FFT, inverse FFT, and separable 2D FFT
- Radix 2 decimation-in-time implementation
- Core code consists of ~50 lines only
- No external dependencies (except libm from standard library)
- C99 compliant

## Usage
Self-explanatory, see [mfft.h](./mfft.h)
```C
// example 
#include "mfft.h"
float complex data[1024]; // requires size to be 2^n 
fft(data, 1024);          // performs FFT inplace
```
## Demo
```
make
./build/test

>>>
test input (time domain):
  n 0 re 1.000000 im 0.000000
  n 1 re 0.707107 im 0.707107
  n 2 re 0.000000 im 1.000000
  n 3 re -0.707107 im 0.707107
  n 4 re -1.000000 im 0.000000
  n 5 re -0.707107 im -0.707107
  n 6 re 0.000000 im -1.000000
  n 7 re 0.707107 im -0.707107
test output (freq domain):
  n 0 re 0.000000 im 0.000000
  n 1 re 8.000000 im 0.000000
  n 2 re 0.000000 im 0.000000
  n 3 re 0.000000 im -0.000000
  n 4 re 0.000000 im 0.000000
  n 5 re 0.000000 im 0.000000
  n 6 re 0.000000 im 0.000000
  n 7 re 0.000000 im 0.000000
benchmarking 1024 point FFT ...
  10000 iterations took 0.154513s
```
