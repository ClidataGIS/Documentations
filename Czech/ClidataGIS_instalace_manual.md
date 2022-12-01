
# Instalace Clidata GIS


## verze 2.20.9.13


# Úvod

Ze zmìnou datové struktury aplikace Clidata (duben 2017) bylo potøeba tyto zmìny provést i v klientských aplikacích 
jako napø. Clidata GIS. Jelikož je to velká zmìna bylo potøeba pøed samotnou úpravou Clidata GIS aplikací 
provést celoústavní sjednocení verzí ClidataGIS. Od této chvíle se budou aktualizovat pouze verze, které vyjdou 
z této instalace. 
Hlavní jsou tyto zmìny:
1. Plošná kontrola a MapViewer nyní budou podporovat pouze aktuální verzi programu ESRI ArcGIS Explorer (verze 3400). Starší a aktuálnì používaná verze ESRI ArcGIS Explorer 1750 již nebude podporována.
2. Prostorové analýzy, budou podporovat pouze ArcGIS 10.6 a novìjší, starší verze ArcGIS 10.1,10.2,10.3,10.4,10.5 již nebudou podporované.

V tomto návodì popíši jednak instalaci na èisté PC (bez pøedchozí verze ClidataGIS) a jednak 
na již existující instalaci ClidataGIS


# Instalaèní soubory

Uložištì instalaèních souboru je na této adrese:  [http://192.168.90.54/kwapplications/GIS/Apps/ZIP/](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/) kde jsou k dispozici tyto instalaèní balíèky [ArcGIS10.6.1.exe](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/ESRI/ArcGIS_Desktop_106_161544.exe)   - instalaèní balík obsahující instalaci ArcGIS 10.6.1

[ArcGIS Explorer 3400.zip](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/ESRI/ArcGISExplorer3400.zip)- instalaèní balík pro ArcGIS Explorer 3400 a ArcGIS Explorer Fonts

[Oracle.zip](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/Oracle/Oracle.zip) -instalaèní balík Oracle klienta pro .NET

[dotNetFx40.exe](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/Microsoft/dotNetFx40_Full_x86_x64.exe)-instalaèní balik pro framework .NET 4.5 (potøeba pro ArcGIS 10.4.1) a novìjší

[MSChart_for_3.5.exe](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/Microsoft/MSChart_for_3.5.exe)-instalaèní balik pro framework .NET 3.5 pro generovani grafu

[ClidataGIS_CHMU_ALL.zip](http://192.168.90.54/kwapplications/GIS/Apps/ZIP/CLIDATA_GIS_ALL_LAST.zip) -kompletni poslední verze instalaèní balík pro instalaci klienta ClidataGIS

na nové PC

**INSTALL_DIR** je instalaèní adresáø, kde jsou všechny staženy a odzipované dílèí aplikace


# Instalace na  PC bez pøedchozí instalace Clidata GIS

 \
Novou instalaci ClidataGIS na PC bez pøedchozí instalace je dle tohoto postupu: \
Instalace aplikací doporuèuji pøes pøíkazový øádek (cmd.exe) spustìný jako administrátor.

Jelikož se bìhem instalace budou zapisovat nìkteré údaje do registru OS je potøeba instalaci dìlat pod daným uživatelem(ideálnì uživatel s doèasnými administrátorskými právy)

PK,MW - potøeba pro aplikaci plošná kontrola (PK) a pro MapViewer (MW)

SA - potøeba pro aplikaci prostorové analýzy pod ArcGIS



1. Instalace Oracle clienta  **_PK,MW,SA_** 	_INSTALL_DIR\Oracle\install_oracleClient.cmd _
2. Instalace DotNet 4.5 pokud již není nainstalovavý v systému  **_PK,MW,SAINSTALL_DIR\dotNet45.exe_**
3. Instalace ArcGIS 10.6.1 **_SA _**    pokud tato verze je již instalovaná na PC tak pøeskoèit tento krok

           _ INSTALL_DIR/ArcGIS_Desktop_106_161544.exe_

4. Instalace ArcGIS Explorer 3400 s volbou Anyone who uses this computer (all Users)  !!!!! **_PK,MW_** \
   	_INSTALL_DIR\ESRI/ArcGIS Explorer 3400\Setup.exe_
5. Instalace ArcGIS Explorer Fonts \
   	_ INSTALL_DIR\ESRI/ArcGISExplorerFonts\Setup.exe_
6. Instalace aplikace ClidataGIS  **_PK,MW,SA_**

    **_Odzipování CLIDATA_GIS_LAST.zip do C:\ClidataGIS\    _**

7. Vytvoøení zástupce na ploše s cestou C:\ClidataGIS\ClidataGIS_Starter.exe CHMU.xml
8. Registrace ClidataGIS do ArcMap  **_SA_**

_C: \ClidataGIS\BIN\Registry_ClidataGIS10.6.cmd_ pro verzi 10.6
_C: \ClidataGIS\BIN\Registry_ClidataGIS10.7.cmd_ pro verzi 10.7
_C: \ClidataGIS\BIN\Registry_ClidataGIS10.8.cmd_ pro verzi 10.8


# Instalace na PC s pøedchozí verzi Clidata GIS

Pokud na PC již existovala pøedchozí verze ClidataGIS je potøeba pøed samotnou instalaci: \
 \
1. Odinstalovat ArcGIS 10.3 a nižší verze \
2. Odinstalovat ArcGIS Explorer  \
4. Smazat složku ClidataGIS10

5. Restart PC

6. Pokraèovat v instalaci jako ve verzi bez pøedchozí instalace ClidataGIS \



# Øešení problému

**Nedaøí se se spustit ArcGIS Explorer z menu ClidataGIS a máte 32bit operaèní systém?**

je potøeba modifikovat soubor C:\ClidataGIS\chmu.xml a parametr *arcExplorer* C:\Program Files (x86)\Explorer (x86)\bin\e3.exe  
upravit na skuteènou cestu, kde je e3.exe soubor (ArcGIS Explorer)  

**Registrace extenze ClidataGIS do aplikace ArcGIS 10.5**

Knihovna Striz.AG10.4.dll je kompilovaná pro verzi ArcGIS 10.4 a k registraci používá program esriRegasm.exe,který je ve složce C:\ClidataGIS\BIN\ESRI. Pokud máte na PC nainstalovanou vyšší verzi ArcGIS napø. 10.5 je potøeba pro registraci spustit soubor esriRegams.exe pro verzi 10.5
z adresáøe 
C:\Program Files (x86)\Common Files\ArcGIS\bin s parametrem Striz.AG10.4.dll /p:Desktop

**Instalace .NET FrameWork 3.5 do Windows 10**

Windows 10. Install .NET Framework 3.5 error 0x800F0954

1. V registrech ve složce HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU nastavit “UseWUServer” na 0 	
2. Restart 	poèítaèe
3. Instalace .NET Framework 3.5 
4. V registrech ve složce HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU nastavit zpìt hodnotu “UseWUServer” na 1	
5. Restartovat poèítaè 	