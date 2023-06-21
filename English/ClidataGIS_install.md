	CLIDATA   GIS

level 1,2
Area Control








***
<div align='center'>
Clidata GIS installation
</div>

***



Ing. Martin Stříž 	(martin@striz.info)    

                                       21. 06. 2023

***
## Installation on new (without previous installation of ClidataGIS) 
***
Clidata GIS installation progress install these programs:
1. Oracle client for .NET framework
2. Microsoft .NET 3.5 framework
3. Microsoft .NET 4 framework
4. MSChart library for .NET
5. ArcGIS Explorer 3400
6. Clidata GIS client

Due to possible problems with users operation system rights I recommend to use **CMD.exe** (run as administrator) to install all programs.

**InstallDir** mean installation directory for ClidataGIS (usually ClidataDB1\INSTALL\ClidataGIS_Install\

**Please follow these steps:**
click on Start button in Windows desktop

click on run type **cmd**
right mouse on cmd and choose run as administrator
in CMD.exe windows continue

go to **InstallDir** (using DOS commands like dir, cd etc)
then cd oracle run **install_oracleClient.cmd** for install **oracle instant** client for .NET

wait for finish

then cd ..

cd .NET

run **dotnetfx35.exe** for install **Microsoft .NET Framework 3.5**

run **dotnetFx40_full_x86_x64.exe** for install **Microsoft .NET Framework 4.0**

run **MsChart_for_3.5.exe** for install **Microsoft Chart library for .NET**

cd ..


cd ArcGISExplorer 3400


run **Setup.exe** for install **ArcGIS Explorer version 3400**

cd ..

cd **ArcGISExplorerFonts**

install ClidataGIS by run **clidataGIS_L2.exe**
***
## Upgrade existing ClidataGIS
***
1. Uninstall previous version of ClidataGIS
2. Install Oracle client for .NET Framework
3. Install ArcGIS Explorer version 3400
4. Install ClidataGIS client


Due to possible problems with users operation system rights I recommend to use **CMD.exe** (run as administrator) to install all programs.

**InstallDir** mean installation directory for ClidataGIS (usually ClidataDB1\INSTALL\ClidataGIS_Install\

**Please follow these steps:**
click on Start button in Windows desktop

click on run type **cmd**
right mouse on cmd and choose run as administrator
in CMD.exe windows continue

go to **InstallDir** (using DOS commands like dir, cd etc)
then cd oracle run **install_oracleClient.cmd** for install **oracle instant** client for .NET

wait for finish

then cd ..

cd .NET

run **dotnetfx35.exe** for install **Microsoft .NET Framework 3.5**

run **dotnetFx40_full_x86_x64.exe** for install **Microsoft .NET Framework 4.0**

run **MsChart_for_3.5.exe** for install **Microsoft Chart library for .NET**

cd ..


cd ArcGISExplorer 3400


run **Setup.exe** for install **ArcGIS Explorer version 3400**

cd ..

cd **ArcGISExplorerFonts**

install ClidataGIS by run **clidataGIS_L2.exe**
***
## Documentations
***

Documetation folder is C:\ClidataGIS\Doc   or on \\USB\ClidataGIS_Install\Doc
***
## Instalace .NET FrameWork 3.5 do Windows 10
***
Windows 10. Install .NET Framework 3.5 error 0x800F0954
Go to    HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU 
 set “UseWUServer” to 0         
restart         computer        
Install         .NET Framework 3.5 (ex. go to ‘Windows Features’, select ‘.NET         Framework 3.5…’ and press OK)
Go to HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU 
 set “UseWUServer” to 1        
restart         computer

