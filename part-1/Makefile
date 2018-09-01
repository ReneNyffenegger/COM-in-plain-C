all: IExample.dll RegIExample.exe IExampleApp.exe UnregIExample.exe

IExampleApp.exe: IExampleApp.c IExample.h
	gcc $< -lole32 -luuid -o $@
#
# -luuid because it exports IID_IClassFactory
#

UnregIExample.exe: UnregIExample.c IExample.h
	gcc $< -lComdlg32 -o $@
#
#  -lComdlg32 because it exports GetOpenFileName
#

RegIExample.exe: RegIExample.c IExample.h
	gcc $< -lComdlg32 -o RegIExample.exe

IExample.dll: IExample.c IExample.h
	gcc -shared IExample.c                       -luuid -Wl,--kill-at -o IExample.dll
#	gcc -shared IExample.c                       -luuid               -o IExample.dll
#	gcc -shared IExample.c iexample\IExample.def -luuid               -o IExample.dll
