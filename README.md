# Paraview-problem-with-OpenFOAM
I am having problems on opening Paraview through OpenFOAM
I installed OpenFOAM V12 and followed the instructions based on the OpenFOAM repository, but i am having troubles when opening Paraview:
This is the issue: 

This was what I ran: cd $FOAM_RUN
cp -r $FOAM_TUTORIALS/incompressibleFluid/pitzDailySteady .
cd pitzDailySteady
blockMesh
foamRun
paraFoam

The simulation ran succesfully, until this: 

Created temporary 'pitzDailySteady.OpenFOAM'
qt.qpa.xcb: could not connect to display 10.255.255.254:0
qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.

Available platform plugins are: eglfs, linuxfb, minimal, minimalegl, offscreen, vnc, wayland-egl, wayland, wayland-xcomposite-egl, wayland-xcomposite-glx, xcb.


paraview:3831 terminated with signal 6 at PC=7fd1b03eeb1c SP=7ffdd9fdcdc0.  Backtrace:
/usr/lib/x86_64-linux-gnu/libc.so.6(pthread_kill+0x11c)[0x7fd1b03eeb1c]
/usr/lib/x86_64-linux-gnu/libc.so.6(gsignal+0x1e)[0x7fd1b039526e]
/usr/lib/x86_64-linux-gnu/libc.so.6(abort+0xdf)[0x7fd1b03788ff]
/usr/lib/x86_64-linux-gnu/libQt5Core.so.5(+0x91104)[0x7fd1ae273104]
/usr/lib/x86_64-linux-gnu/libQt5Gui.so.5(_ZN22QGuiApplicationPrivate25createPlatformIntegrationEv+0x17ad)[0x7fd1ae8916dd]
/usr/lib/x86_64-linux-gnu/libQt5Gui.so.5(_ZN22QGuiApplicationPrivate21createEventDispatcherEv+0x40)[0x7fd1ae891c20]
/usr/lib/x86_64-linux-gnu/libQt5Core.so.5(_ZN23QCoreApplicationPrivate4initEv+0x8e5)[0x7fd1ae4c0ff5]
/usr/lib/x86_64-linux-gnu/libQt5Gui.so.5(_ZN22QGuiApplicationPrivate4initEv+0x2f)[0x7fd1ae894b9f]
/usr/lib/x86_64-linux-gnu/libQt5Widgets.so.5(_ZN19QApplicationPrivate4initEv+0x15)[0x7fd1af96e5b5]
paraview(+0x112c4)[0x5576e99862c4]
/usr/lib/x86_64-linux-gnu/libc.so.6(+0x2a1ca)[0x7fd1b037a1ca]
/usr/lib/x86_64-linux-gnu/libc.so.6(__libc_start_main+0x8b)[0x7fd1b037a28b]
paraview(+0x9b05)[0x5576e997eb05]

I had this problem and tried to solve it with:

 export LIBGL_ALWAYS_SOFTWARE=1

But the issue remains
