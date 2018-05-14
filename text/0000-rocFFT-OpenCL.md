- Feature Name: rocFFT OpenCL support 
- Start Date: 2018-05-15 
- RFC PR: (leave this empty)
- ROCm Issue: (leave this empty)

# Summary
[summary]: #summary

To support the OpenCL community, the rocFFT library should provide
means for it to be used in OpenCL projects.

# Motivation
[motivation]: #motivation

FFTs are often used components in scientific and engineering computing
and therefore there is a broad set of use-cases where computing FFTs on
ROCm platforms would be of great benefit (e.g. GROMACS, OpenMM / Folding@HOME, etc.)

# Detailed design
[design]: #detailed-design

* Short-term solution: use `clCreateProgramWithBinary` to load precompiled FFT kernels;
* Longer-term more complete solution: implemet the `rocfft.h` API for OpenCL;
* Device-side callable 1D FFT kernels would also be very valuable to be
developed for release when the required OpenCL support also lands in a future ROCm
stack release.

# Drawbacks
[drawbacks]: #drawbacks

Effort may be better invested in clFFT and its compatibility with the ROCm toolchain
as well as early high quality and high performance support for recent AMD hardware.

# Alternatives
[alternatives]: #alternatives

Other designs: -
Impact of reject: No high performance FFT will be available for portable GPU applications on AMD GPUs.

# Unresolved questions
[unresolved]: #unresolved-questions

The detailed design is really up to the rocFFT and OpenCL runtime's dev.

