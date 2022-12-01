
# Instalace Clidata GIS


## verze 2.20.9.13


# �vod

Ze zm�nou datov� struktury aplikace Clidata (duben 2017) bylo pot�eba tyto zm�ny prov�st i v klientsk�ch aplikac�ch 
jako nap�. Clidata GIS. Jeliko� je to velk� zm�na bylo pot�eba p�ed samotnou �pravou Clidata GIS aplikac� 
prov�st celo�stavn� sjednocen� verz� ClidataGIS. Od t�to chv�le se budou aktualizovat pouze verze, kter� vyjdou 
z t�to instalace. 
Hlavn� jsou tyto zm�ny:
1. Plo�n� kontrola a MapViewer nyn� budou podporovat pouze aktu�ln� verzi programu ESRI ArcGIS Explorer (verze 3400). Star�� a aktu�ln� pou��van� verze ESRI ArcGIS Explorer 1750 ji� nebude podporov�na.
2. Prostorov� anal�zy, budou podporovat pouze ArcGIS 10.6 a nov�j��, star�� verze ArcGIS 10.1,10.2,10.3,10.4,10.5 ji� nebudou podporovan�.

V tomto n�vod� pop�i jednak instalaci na �ist� PC (bez p�edchoz� verze ClidataGIS) a jednak 
na ji� existuj�c� instalaci ClidataGIS


# Instala�n� soubory

Ulo�i�t� instala�n�ch souboru je na t�to adrese:  [http://192.168.90.54/kwapplications/GIS/Apps/ZIP/](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/) kde jsou k dispozici tyto instala�n� bal��ky [ArcGIS10.6.1.exe](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/ESRI/ArcGIS_Desktop_106_161544.exe)   - instala�n� bal�k obsahuj�c� instalaci ArcGIS 10.6.1

[ArcGIS Explorer 3400.zip](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/ESRI/ArcGISExplorer3400.zip)- instala�n� bal�k pro ArcGIS Explorer 3400 a ArcGIS Explorer Fonts

[Oracle.zip](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/Oracle/Oracle.zip) -instala�n� bal�k Oracle klienta pro .NET

[dotNetFx40.exe](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/Microsoft/dotNetFx40_Full_x86_x64.exe)-instala�n� balik pro framework .NET 4.5 (pot�eba pro ArcGIS 10.4.1) a nov�j��

[MSChart_for_3.5.exe](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/Microsoft/MSChart_for_3.5.exe)-instala�n� balik pro framework .NET 3.5 pro generovani grafu

[ClidataGIS_CHMU_ALL.zip](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/CLIDATA_GIS_ALL_LAST.zip) -kompletni posledn� verze instala�n� bal�k pro instalaci klienta ClidataGIS

na nov� PC

**INSTALL_DIR** je instala�n� adres��, kde jsou v�echny sta�eny a odzipovan� d�l�� aplikace


# Instalace na  PC bez p�edchoz� instalace Clidata GIS

 \
Novou instalaci ClidataGIS na PC bez p�edchoz� instalace je dle tohoto postupu: \
Instalace aplikac� doporu�uji p�es p��kazov� ��dek (cmd.exe) spust�n� jako administr�tor.

Jeliko� se b�hem instalace budou zapisovat n�kter� �daje do registru OS je pot�eba instalaci d�lat pod dan�m u�ivatelem(ide�ln� u�ivatel s do�asn�mi administr�torsk�mi pr�vy)

PK,MW - pot�eba pro aplikaci plo�n� kontrola (PK) a pro MapViewer (MW)

SA - pot�eba pro aplikaci prostorov� anal�zy pod ArcGIS



1. Instalace Oracle clienta  **_PK,MW,SA_** 	_INSTALL_DIR\Oracle\install_oracleClient.cmd _
2. Instalace DotNet 4.5 pokud ji� nen� nainstalovav� v syst�mu  **_PK,MW,SAINSTALL_DIR\dotNet45.exe_**
3. Instalace ArcGIS 10.6.1 **_SA _**    pokud tato verze je ji� instalovan� na PC tak p�esko�it tento krok

           _ INSTALL_DIR/ArcGIS_Desktop_106_161544.exe_

4. Instalace ArcGIS Explorer 3400 s volbou Anyone who uses this computer (all Users)  !!!!! **_PK,MW_** \
   	_INSTALL_DIR\ESRI/ArcGIS Explorer 3400\Setup.exe_
5. Instalace ArcGIS Explorer Fonts \
   	_ INSTALL_DIR\ESRI/ArcGISExplorerFonts\Setup.exe_
6. Instalace aplikace ClidataGIS  **_PK,MW,SA_**

    **_Odzipov�n� CLIDATA_GIS_LAST.zip do C:\ClidataGIS\    _**

7. Vytvo�en� z�stupce na plo�e s cestou C:\ClidataGIS\ClidataGIS_Starter.exe CHMU.xml
8. Registrace ClidataGIS do ArcMap  **_SA_**

_C: \ClidataGIS\BIN\Registry_ClidataGIS10.6.cmd_ pro verzi 10.6
_C: \ClidataGIS\BIN\Registry_ClidataGIS10.7.cmd_ pro verzi 10.7
_C: \ClidataGIS\BIN\Registry_ClidataGIS10.8.cmd_ pro verzi 10.8


# Instalace na PC s p�edchoz� verzi Clidata GIS

Pokud na PC ji� existovala p�edchoz� verze ClidataGIS je pot�eba p�ed samotnou instalaci: \
 \
1. Odinstalovat ArcGIS 10.3 a ni��� verze \
2. Odinstalovat ArcGIS Explorer  \
4. Smazat slo�ku ClidataGIS10

5. Restart PC

6. Pokra�ovat v instalaci jako ve verzi bez p�edchoz� instalace ClidataGIS \



# �e�en� probl�mu

**Neda�� se se spustit ArcGIS Explorer z menu ClidataGIS a m�te 32bit opera�n� syst�m?**

je pot�eba modifikovat soubor C:\ClidataGIS\chmu.xml a parametr *arcExplorer* C:\Program Files (x86)\Explorer (x86)\bin\e3.exe  
upravit na skute�nou cestu, kde je e3.exe soubor (ArcGIS Explorer)  

**Registrace extenze ClidataGIS do aplikace ArcGIS 10.5**

Knihovna Striz.AG10.4.dll je kompilovan� pro verzi ArcGIS 10.4 a k registraci pou��v� program esriRegasm.exe,kter� je ve slo�ce C:\ClidataGIS\BIN\ESRI. Pokud m�te na PC nainstalovanou vy��� verzi ArcGIS nap�. 10.5 je pot�eba pro registraci spustit soubor esriRegams.exe pro verzi 10.5
z adres��e 
C:\Program Files (x86)\Common Files\ArcGIS\bin s parametrem Striz.AG10.4.dll /p:Desktop

**Instalace .NET FrameWork 3.5 do Windows 10**

Windows 10. Install .NET Framework 3.5 error 0x800F0954

1. V registrech ve slo�ce HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU nastavit �UseWUServer� na 0 	
2. Restart 	po��ta�e
3. Instalace .NET Framework 3.5 
4. V registrech ve slo�ce HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU nastavit zp�t hodnotu �UseWUServer� na 1	
5. Restartovat po��ta� 	