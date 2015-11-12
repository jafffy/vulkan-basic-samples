# Vulkan Samples Kit
  - This repository is a collection of Vulkan C++ sample applications.
  - Run the following script to obtain a short description of all or a 
    specific sample:
    `$ src/get-short-descripts.sh`
  - Run the following script to obtain a more detailed description of all
    samples with a long description set:
    `$ src/get-descripts.sh`

## Requirements/Dependencies
  - A recent version of the LunarG Vulkan SDK must be installed on the system.
    In addtion to the Vulkan headers and libraries, the SDK also includes the
    glslang components necessary to build the sample progams.
  - Linux package dependencies:
    - Vulkan SDK required packages
    - cmake
  - Windows dependencies include:
    - Vulkan SDK required components
    - cmake
  - Note that if you have a LoaderAndTools repository, and/or a glslang
    repository that are file system peers to VulkanSamplesKit, cmake will
    look in those repositories for headers and libraries before looking in
    SDK or system locations.  Build directories in those repositories should
    be named "build".

## Kit Structure
  - The Vulkan Samples Kit is a set of source and data files in a specific
    directory hierarchy:
      - data/ - static data files used in the samples, ie images, shaders, etc; 
        Vulkan-version-specific files will reside in directories named by the
        version (i.e. vk1.0)
      - ext/ - external third party components outside of the Vulkan SDK and
        samples framework (glm)
      - src/ - samples source code, where sample file name is prefixed by Vulkan
        version (i.e. vk1.0-instance.cpp)
      - utils/ - source code for common utilities used by the sample programs

## Sample progression
  - In general, the samples are not interrelated, but there is a progression
      among some of the samples that lead to drawing a cube.  Start with the
      instance sample, then device, initcommandbuffer, initswapchain, initdepthbuffer,
      inituniformbuffer, descriptor_pipeline_layouts, initrenderpass, initshaders,
      initframebuffers, vertexbuffer, allocdescriptorsets, initpipeline, and they
      culminate in the drawcube sample.  Each sample uses utility routines from
      the code from previous samples to get to the point to show something new.
      The drawtexturedcube sample takes all of the drawcube code and adds texturing.

## Building the Vulkan Samples Kit
- Linux:
  ```
  $ cmake -H. -Bbuild
  $ make -C build 
  ```

- Windows:  
From a PowerShell window, first build glslang:
  ```
  PS > cd C:\VulkanSDK\<version>\glslang
  PS > mkdir build
  PS > cd build
  PS > cmake -G "Visual Studio 12 Win64" ..
  ```
  Open the glslang.sln file in the build folder with Microsoft Visual Studio and build the solution in both Debug and Release mode.  

  Next build the Vulkan Samples:
  ```
  PS > cd C:\VulkanSDK\<version>\VkSamples
  PS > mkdir build
  PS > cd build
  PS > cmake -G "Visual Studio 12 Win64" ..
  ```
  Open the VULKAN_SAMPLES.sln file in the build folder with Microsoft Visual Studio and build the solution.
## Contributing
  Refer to the README.contrib file for specific info regarding contributing to
  the Vulkan samples creation effort.

