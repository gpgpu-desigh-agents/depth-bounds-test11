# AMD Depth Bounds Test Driver Extension Sample
<img src="depthboundstest11/media/Thumbnail.png" width="480" height="284" />

The DepthBoundsTest11 DirectX 11 sample shows how to use the Depth Bounds driver extension. Depth Bounds Test is a feature on AMD Radeon&trade; HD 7000 series cards and later. It checks to see if the current depth values are within a certain range (bounds). Drawing is allowed for pixels where the depth is in range, and culled for depths outside the bounds. Note that the comparison is made with the current depth values in the depth buffer, not the depth value of the pixel to be written. The sample demonstrates a performance improvement you can get with this feature when using deferred rendering.

The depth bounds test functionality is accessed through the AMD GPU Services (AGS) library. For more information on AGS, including samples, visit the AGS SDK repository:
https://github.com/GPGPU-Desigh-Agents/AGS_SDK

### Prerequisites
* AMD Radeon&trade; GCN-based GPU (HD 7000 series or newer)
* 64-bit Windows&reg; 7 (SP1 with the [Platform Update](https://msdn.microsoft.com/en-us/library/windows/desktop/jj863687.aspx)), Windows&reg; 8.1, or Windows&reg; 10
* Visual Studio&reg; 2012, Visual Studio&reg; 2013, or Visual Studio&reg; 2015

### Getting Started
* Visual Studio solutions for VS2012, VS2013, and VS2015 can be found in the `depthboundstest11\build` directory.
* Additional documentation can be found in the `depthboundstest11\doc` directory.

### Premake
The Visual Studio solutions and projects in this repo were generated with Premake. To generate the project files yourself (for another version of Visual Studio, for example), open a command prompt in the `premake` directory and execute the following command:

* `update_vs_files_for_dx11_sample.bat depthboundstest11 [action]`
* For example: `update_vs_files_for_dx11_sample.bat depthboundstest11 vs2010`

This version of Premake has been modified from the stock version to use the property sheet technique for the Windows SDK from this [Visual C++ Team blog post](http://blogs.msdn.com/b/vcblog/archive/2012/11/23/using-the-windows-8-sdk-with-visual-studio-2010-configuring-multiple-projects.aspx). The technique was originally described for using the Windows 8.0 SDK with Visual Studio 2010, but it applies more generally to using newer versions of the Windows SDK with older versions of Visual Studio.

The default SDK for a particular version of Visual Studio (for 2012 or higher) is installed as part of Visual Studio installation. This default (Windows 8.0 SDK for Visual Studio 2012 and Windows 8.1 SDK for Visual Studio 2013) will be used if newer SDKs do not exist on the user's machine. However, the projects generated with this version of Premake will use the next higher SDK (Windows 8.1 SDK for Visual Studio 2012 and Windows 10 SDK with Visual Studio 2013), if the newer SDKs exist on the user's machine.

For Visual Studio 2015, this version of Premake adds the `WindowsTargetPlatformVersion` element to the project file to specify which version of the Windows SDK will be used. To change `WindowsTargetPlatformVersion` for Visual Studio 2015, change the value for `_AMD_WIN_SDK_VERSION` in `premake\amd_premake_util.lua` and regenerate the Visual Studio files.

### Third-Party Software
* DXUT is distributed under the terms of the MIT License. See `dxut\MIT.txt`.
* Premake is distributed under the terms of the BSD License. See `premake\LICENSE.txt`.

### Attribution
* AMD, the AMD Arrow logo, Radeon, and combinations thereof are either registered trademarks or trademarks of Advanced Micro Devices, Inc. in the United States and/or other countries.
* Microsoft, DirectX, Visual Studio, and Windows are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries.
