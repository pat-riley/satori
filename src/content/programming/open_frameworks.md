#Open Framworks

##What is it

Open Source C++ toolkit designed to assist the creative process by provising a simple and intuitive framework for experimentation. The toolkit is designed to work as a gerneral purpose glue, and wraps together several commonly used libraries including.

*OpenGL, GLEW, GLUT, FLFW. libtess2, and Cairo for graphics
*rtAudio, PortAudio or FMOD and Kiss FFT for audio input output and analysis
*FreeType for fonts
*FreeImage for image saving and loading
*Quicktime and videoInput for video playback and grabbing
*Poco for a variety of utilities

##Installation

1. Download openFrameworks
2. `xcode-select --install` to get xcode command line tools
3. Place OF in root folder, Also known as `OF_ROOT`
4. Open up an example and compile

###Errors and Debugging

Two major kind of errors

1.Compilation Errors - typos, bad build settings, they keep your app from being compiled at all. They are usually traced down to a specific line.
2.Runtime Errors - errors you get after the app has launhed and have all cap names like `EXC_BAD_ACCESS`

##File Structure

####addons

The "core" openFrameworks contains only the most essential functionality. Everything in the addons folder can be added to an application piecemeal. This includes stuff like reading an XML file, loading a 3D model, or using the computer vision library, openCV.

####apps

This is where the applications that you make will be stored, and where you will be working most of the time. You will notice that there are already a folder in "apps" called "myApps".

####examples

This folder contains example applications that illustrate some of the things that openFrameworks can do.

####libs

This folder contains all the libraries that openFrameworks uses as well as the ofCore.

###App Structure

`void testAPp::setup(){}`

This function is called (i.e.: any code that you’ve put inside the curly brackets runs) at the very beginning of the life of your application, before your program window opens. So, let’s say, for instance, you wanted to set the size of the window. You probably want this to happen before the window actually opens, so setup would be a good place for that.

`void testApp::update(){}` `void testApp::draw(){}`

These two functions are called back to back as soon right after setup is called. First update, and then draw, as many times as



























