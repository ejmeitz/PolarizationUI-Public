# PolarizationUI-Public
This is a description of my private repository that contains my code from working in the Lake lab at Washington University in St. Louis.


# This project is an effort to create a graphical user interface for use in reflectance and transmission mode quantitative polarized light imaging. The project was supervised by the Lake lab at Washington University in St. Louis. Unfortunately, the code is private, but you can still read about it here.

******About the GUI:******
The GUI was designed for use with the FLIR Blackfly USB 3.0 camera with a SONY IMX250MZR monochrome polarization sensor. This camera can be operated at of 50 FPS and 2448 x 2048 resolution while using the GUI. The UI was designed for use with reflected and transmission mode QPLI in the Lake lab at Washington University in St. Louis. The UI allowed the Lake lab to customize their imaging setup and acuire data with higher resolution, frame rate and fidelity. 

******How to Use the GUI:****** (for more detailed instructions read the Protocol.docx file)
1. Connect the camera through a USB 3.0 port, the light should flash green
2. Open the GUI
3. Choose the resolution and FPS
4. Click "Browse" to choose the location where your data will be saved (pick a local SSD, no cloud storage or external drives)
5. Click the check box next to the FPS box to lock in your selections and connect the GUI to the camera
6. Press begin acquisition to start saving data or acquire single to take a single image
7. To change the settings press disconnect
8. The data will be saved as an h5 file (download H5 viewer from the internet to open)


******System Requirements******
-Windows x64
-512GB SSD (faster the write speed the better)
-At least 50GB of free space -- the files size is not limited and will grow with the length of acquisition (size ~ (xRes)*(yRes)*(FPS)*(duration of run))
-16GB RAM (24+ GB preferred)
-USB 3.0 
-1980 x 1080 screen resolution (higher resolution  has not been tested)


******Installation******
1. Download the .msi file from GitHub and run it!

******Building Source Code******
1. Extract dependencies.7z 
2. Copy all of the .dll files from that folder into a folder called "bin"
3. Create a new folder inside of bin called "platforms" and place the qwindows.dll file inside (if you have Qt you could also run "windeployqt --quick ." after build)
4. Copy all of the files from "XML" into "bin"
5. Open "BlackflyPolarizationGUI.sln" with VS2019. 
6. Build the program using visual studio

	Note: If you want to rebuild the installer make sure you have the VS extension for installer projects added. 
	Furthermore, it may throw errors and that is likely because it can't find the dll files. 
	To change the location right click the Installer Project and click "View" then "File System". Then click the application folder on the left.
	This is the folder that the installer will build on your computer. It's essentially the bin folder. Right click the applcation folder and then click "Add" and "Assembly".
	Browse for the files needed (which should be all of the files already in there) which can be found in the "Dependencies" & "XML" (no debug dll's needed). Delete the old files.
	To see the path of a file right click the file and hit properties.


******Program Versions Used:******
-Spinnaker SDK v 1.29.05_x64 (if version not avaiable all of the dlls from here must be replaced with new ones or contact FLIR for the executable)
-Cmake-hdf5-1.12.0 (static linking option chosen in build)
-Qt 5.12.4 MSVC 2015
-OpenCV 4.3.0 vc14

Notes:
-Camera MUST be plugged in through a USB 3.0 or faster port--"Current Speed" node in SpinView should be super speed
-Be 100% sure you choose an SSD to write to or things will explode 
