# How-Do
To build the KfwRibbon in Visual Studio you have to build the parent src directory using the makefile.in to create dependency libs

## This is the part to build KRB5 sources (kfw - KerberOS for Windows)
1. start Windows CMD
2. cd to krb5 src (branch of kfw tag)
3. run Visual Studio environment 
  call "C:\Program Files\Microsoft Visual Studio\2022\Professional\VC\Auxiliary\Build\vcvars64.bat"
4. set PATH=%PATH%;"%WindowsSdkVerBinPath%"\x86  # To get uicc.exe
  set PATH=%PATH%;C:\Program Files (x86)\Windows Kits\10\bin\10.0.26100.0\x86
5. set PATH of Wix toolset
  set PATH=%PATH%;C:\Program Files (x86)\WiX Toolset v3.14\bin
6. set KRB_INSTALL_DIR=\path\to\dir    # Where bin/include/lib lives
  set KRB_INSTALL_DIR=C:\krb5install

7. set NO_LEASH=1 (To skip building the graphical ticket manager, run "set NO_LEASH=1"
before building, and do not build the installer.) 
8. nmake -f Makefile.in prep-windows
9. nmake