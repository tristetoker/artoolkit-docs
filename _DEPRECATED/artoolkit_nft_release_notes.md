# ARToolkit NFT Release Notes

Latest release: 3.49.0

__TOC__

README
------

    Read me for ARToolKit NFT.
    ==========================


    Contents.
    ---------

    About this archive.
    Building the examples.
    Running the examples.
    Creating your own feature maps and feature sets.
    Changes in this release.
    Known issues in this release.
    Changes in earlier releases.


    About this archive.
    -------------------

    This archive contains the ARToolKit NFT libraries, utilities and examples, version 3.49.0.

    ARToolKit NFT version 3.49.0 is released to you under a proprietary license. Please note that your license terms impose various restrictions on distribution of ARToolKit in both source and binary forms. Legal remedy will be sought by ARToolworks, Inc. for any unauthorised distribution.

    Your license terms may entitle you to hot fixes and / or upgrades to ARToolKit NFT version 3.49.0. Please contact us for more information.

    ARToolKit NFT is designed to build on Linux, Windows, and Macintosh OS X platforms.

    This archive was assembled by:
        Philip Lamb
        ARToolworks, Inc.
        http://www.artoolworks.com
        2011-03-30


    Building the examples.
    ----------------------

    ARToolKit NFT is supplied with pre-built binaries for all of the examples (as well as the libraries and utilities). If you want to experiment with the examples right away, skip to the next section.

    ARToolKit NFT's example(s) functions as both a demo of the NFT functionality, as well as a template which you can copy, to change various options and to add your own customisations. You will want to build your own example applications from source at some point.

    The most up-to-date build instructions can always be found in the ARToolworks support library at http://www.artoolworks.com/support/library/ARToolKit_NFT.

    *** Required software/source packages:

    *   ARToolKit Professional v4.5.1.
        You must have ARToolKit Professional installed prior to attempting to build any ARToolKit NFT examples. The ARTOOLKIT_4_ROOT environment variable must be defined and point the root of the ARToolKit4 directory. On Windows, this environment variable is set by the ARToolKit Professional installer. On Mac OS X and Linux, you will need to manually run the script 'share/artoolkit4-setenv' inside your ARToolKit Professional installation.

    *   A compiler.
        *   Windows: Microsoft Visual Studio 2010, and Microsoft Visual Studio 2008 SP1 are supported.
        *   Mac OS X: Xcode tools v3.1 under Mac OS X 10.5 or later is required. These may be obtained free from Apple at http://developer.apple.com/tools/xcode/.
        *   Linux: GCC 4.4 is recommended.

    *   OpenGL

    *   GLUT; required to build the examples. (libARgsub_lite provides equivalent functionality to libARgsub without requiring GLUT).
        *   Windows: GLUT 3.7.6 is included with ARToolKit NFT.
        *   Mac OS X: included in OS.
        *   Linux: GLUT should be available in your distribution (e.g. packages freeglut3-dev and xorg-dev). Otherwise, GLUT is included in the MESA 3D libraries: [http://mesa3d.sourceforge.net/]

    *   OpenCV; required by libKPM.
        *   Windows: http://downloads.sourceforge.net/opencvlibrary/OpenCV_1.0.exe
        *   Mac OS X: Mark Asbach has created OpenCV binaries for Macintosh in the form of a Private Framework, and this is the OpenCV variant supported by ARToolKit Professional. Click here to download Mark Asbach's OpenCV binary for Macintosh. Once downloaded, create a folder inside your ARToolKit folder named "Frameworks" and drag OpenCV.framework into it.
        *   Linux: http://downloads.sourceforge.net/opencvlibrary/opencv-1.0.0.tar.gz

    *   A video capture source
        *   Windows: By default, on Windows ARToolKit Professional's video library (libARvideo) uses Microsoft's DirectShow as a video source. Unfortunately, this requires installation of the DirectX SDK and either the Windows SDK or the DirectShow package from the Microsoft Platform SDK to compile libARvideo. Please see the separate page Building libARvideo using DirectShow. Alternative video sources on Windows include:
            *    QuickTime, either using the VideoDigitizer or movie files or streams. Please see the separate page Building libARvideo using QuickTime.
            *    Thomas Pintaric's DSVideoLib which is the default video source for ARToolKit v2.x (N.B.: DSVideoLib is now LGPL licensed and may be used in proprietary software.)
            *    Point Grey's flycapture SDK (only for use with Point Grey Cameras).
            *    Canon's HDCam64 camera control library (Canon HDCam64 users only).
        *   Mac OS X: QuickTime v6.4 or later is required, and is included in all versions of Mac OS X > 10.3.
        *   Linux: Video4Linux (e.g. package libv4l-dev), or libdc1394 (e.g. package libdc1394-22-dev), or gstreamer (e.g. package libgstreamer0.10-dev) is required.


    *** Building ARToolKit NFT examples:

    Windows
        *   Open the ARToolKit NFT.sln file inside the appropriate directory in side the "VisualStudio" directory.
        *   Build the sample applications.

    Mac OS X
        *   Open the ARToolKitNFT.xcodeproj, found inside the Xcode folder.
        *   Select a target to build.

    Linux
        *    Building proceeds with the usual steps ./Configure; make.


    Running the examples:
    ---------------------

    ARToolKit NFT includes some examples demonstrating ARToolKit NFT programming techniques. The executables for these applications can be found in the bin directory inside your ARToolKit NFT installation.

    The simpleNFT2 example demonstrates NFT 1.0 + 2.0 markerless tracking. The NFT data set to use must be specified as a command-line argument. A sample dataset is provided in the directory bin/Data/pinball/ and in the file bin/Data/pinball.kpm.

        * Print the image bin/Data/pinball/pinball.jpg
        * Open a command-line window (Terminal on Mac OS X/Linux, cmd.exe on Windows).
        * Navigate to your ARToolKitNFT/bin directory.
        * The invocation is slightly different depending on the platform:
            Windows: simpleNFT2.exe Data\pinball
            Mac OS X: ./simpleNFT2.app/Contents/MacOS/simpleNFT2 Data/pinball
            Linux: ./simpleNFT2 Data/pinball

    The simpleNFT example demonstrates a less resource-intensive technique using a combination of marker tracking and NFT 1.0 tracking. The NFT data set to use must be specified as a command-line argument. A sample dataset is provided in the directory bin/Data/MagicLand3/.

        * Print the image bin/Data/MagicLand3/MagicLand3.jpg
        * Open a command-line window (Terminal on Mac OS X/Linux, cmd.exe on Windows).
        * Navigate to your ARToolKitNFT/bin directory.
        * The invocation is slightly different depending on the platform:
            Windows: simpleNFT.exe Data\MagicLand3\config.dat
            Mac OS X: ./simpleNFT.app/Contents/MacOS/simpleNFT Data/MagicLand3/config.dat
            Linux: ./simpleNFT Data/MagicLand3/config.dat


    Creating your own data sets.
    ------------------------------------------------

    ARToolKit NFT comes with all tools you need to create your own data sets from source image files.

    See the tutorials in the ARToolworks support library at http://www.artoolworks.com/support/library/ARToolKit_NFT for instructions on how to use the tools.


    Changes in version 3.49.0 (this release) (2011-03-30).
    ------------------------------------------------------
    New features:
    - Addition of the markerless NFT 2.0 (KPM) tracker.

    Enhancements:
    - Updated core libraries to work with ARToolKit Professional v4.5.1.
    - Many JPEG-creation tools fail to correctly write the JPEG resolution (DPI). ARToolKit NFT will manually query the user to enter the resolution when it cannot be read from the JPEG file.
    - Windows: Microsoft Visual Studio 2010 support has been added. Visual Studio 2005 SP1 and Visual Studio .NET 2003 support has been dropped.


    Changes in version 3.48.1 (2010-08-24).
    ---------------------------------------
    Bug fixes:
    - Fixes to support changes in path handling in ARToolKit v4.4.3.


    Changes in version 3.48.0 (2009-07-16).
    ---------------------------------------
    New features:
    - Support for running the NFT process asynchronously in a secondary thread.
    - Support for more than one NFT process, allowing use in stereo NFT applications.


    Known issues in this release.
    -----------------------------
    - ARToolKit NFT is an emerging product in an active area of research in computer graphics and image processing. There are known limitations to NFT techniques. Please consult ARToolworks reference documentation to help understand how to get the best performance from ARToolKit NFT.
    - Windows 64-bit support will resume in the next release.


    Changes in earlier releases.
    ----------------------------
    Please see the file ChangeLog.txt.

    --
    EOF

ChangeLog
---------

    ARToolKit NFT ChangeLog.
    ========================


    Changes in version 3.49.0 (this release) (2011-03-30).
    ------------------------------------------------------
    New features:
    - Addition of the markerless NFT 2.0 (KPM) tracker.

    Enhancements:
    - Updated core libraries to work with ARToolKit Professional v4.5.1.
    - Many JPEG-creation tools fail to correctly write the JPEG resolution (DPI). ARToolKit NFT will manually query the user to enter the resolution when it cannot be read from the JPEG file.
    - Windows: Microsoft Visual Studio 2010 support has been added. Visual Studio 2005 SP1 and Visual Studio .NET 2003 support has been dropped.


    Changes in version 3.48.1 (2010-08-24).
    ---------------------------------------
    Bug fixes:
    - Fixes to support changes in path handling in ARToolKit v4.4.3.


    Changes in version 3.48.0  (2009-07-16).
    ----------------------------------------
    New features:
    - Support for running the NFT process asynchronously in a secondary thread.
    - Support for more than one NFT process, allowing use in stereo NFT applications.


    Changes in version 3.24.3 (2008-11-06).
    ---------------------------------------
    Enhancements:
    - Marker files can now optionally reference matrix (2D-barcode) markers. simpleNFT has been updated to demonstrate usage.

    Bug fixes:
    - genMarkerSet now correctly displays which markers it wants to include.
    - genMarkerSet now writes relative paths to pattern files into the marker file.


    Changes in version 3.24.2 (2008-02-11).
    ---------------------------------------
    Enhancements:
    - Loading surfaceSets no longer requires the working directory to be set to the directory of the executable.


    Changes in version 3.24.1 (2008-01-10).
    ---------------------------------------
    New features:
    - Experimental support for matching of camera images against Gaussian-blurred versions of the template images is now available. This may provide improved recognition in select situations. The default number of blur levels is determined at compile time and is fixed at 5 for binary releases. The blurred versions are generated by genImageSet utility, so you will have to rebuild old imagesets (using genImageSet) for them to work with the new version of ARToolKit NFT.
    - A utility (checkResolution) has been added to allow empirical determination of image DPIs for a given range of camera movement.

    Enhancements:
    - Optimizations in genFeatureSet have resulted in feature set extraction speed being increased by as much as 100 times for certain types of images, reducing the time for this step from several hours to a few minutes for some images.
    - Feature similarity during the online matching process can now be adjusted from 0 (accept any match) to 1.0 (accept only perfect match). The default value is 0.7.
    - Tracking history is now handled in libAR2, rather than being needed to be implemented in the calling application, greatly simplifying control flow in simpleNFT's mainLoop().
    - Support for ARGB-format video frames has been added, enabling full compatibility with Mac OS X.
    - Compatibility with ARToolKit 4.3's news lens distortion model.

    Bug fixes:
    - Fixed a bug when during online tracking, when many more feature candidates were available than required, a crash occurred. Now, only the best matches will be used.

    Other changes:
    - A variety of setters and getters and cleanup routines have been added (as listed in AR2/tracking.h, plus ar2FreeFeatureSet, ar2FreeMarkerSet, ar2FreeImageSet).

    Changes in version 3.20.1 (2007-04-03).
    ---------------------------------------
    - Update to enhanced camera parameter handling introduced in ARToolKit Professional v4.1.1.
    - Reorganised the simpleNFT mainLoop for clarity.
    - Changed default NFT mode to FRAME_IMAGE.


    Changes in version 3.20 (2006-02-03).
    -------------------------------------
    - Additions by Jens Hopfer, HITLab NZ
    - Substantial update for ARToolKit4.1 integration by Philip Lamb, ARToolworks, Inc.
    - Begain maintaining ChangeLog in releases.

    --
    EOF

[Category:ARToolKit NFT](/Category:ARToolKit_NFT "wikilink")