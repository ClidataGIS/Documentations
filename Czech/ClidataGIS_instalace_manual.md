***
<div align='center'>
Instalace Clidata GIS
</div>

***


## Úvod

Ze změnou datové struktury aplikace Clidata (duben 2017) bylo potřeba tyto změny provést i v klientských aplikacích jako např. Clidata GIS. Jelikož je to velká změna bylo potřeba před samotnou úpravou Clidata GIS aplikací provést celoústavní sjednocení verzí ClidataGIS. Od této chvíle se budou aktualizovat pouze verze, které vyjdou 
z této instalace.  
Hlavní jsou tyto změny:
1. Plošná kontrola a MapViewer nyní budou podporovat pouze aktuální verzi programu ESRI ArcGIS Explorer (verze 3400). Starší a aktuálně používaná verze ESRI ArcGIS Explorer 1750 již nebude podporována.
2. Prostorové analýzy, budou podporovat pouze ArcGIS 10.6 a novější, starší verze ArcGIS 10.1,10.2,10.3,10.4,10.5 již nebudou podporované.

V tomto návodě popíši jednak instalaci na čisté PC (bez předchozí verze ClidataGIS) a jednak na již existující instalaci ClidataGIS
  
***
## Instalační soubory
  

Uložiště instalačních souboru je na této adrese:  
[http://192.168.90.66/kwapplications/GIS/Apps/ZIP/](http://192.168.90.66/kwapplications/GIS/Apps/ZIP/)  
kde jsou k dispozici tyto instalační balíčky:  

[ArcGIS10.6.1.exe](http://192.168.90.66/kwapplications/GIS/Apps/ZIP/ESRI/ArcGIS_Desktop_106_161544.exe)   - instalační balík obsahující instalaci ArcGIS 10.6.1

[ArcGIS Explorer 3400.zip](http://192.168.90.66/kwapplications/GIS/Apps/ZIP/ESRI/ArcGISExplorer3400.zip)- instalační balík pro ArcGIS Explorer 3400 a ArcGIS Explorer Fonts

[Oracle.zip](http://192.168.90.66/kwapplications/GIS/Apps/ZIP/Oracle/Oracle.zip) -instalační balík Oracle klienta pro .NET

[dotNetFx40.exe](http://192.168.90.66/kwapplications/GIS/Apps/ZIP/Microsoft/dotNetFx40_Full_x86_x64.exe)-instalační balik pro framework .NET 4.5 (potřeba pro ArcGIS 10.4.1) a novější

[MSChart_for_3.5.exe](http://192.168.90.66/kwapplications/GIS/Apps/ZIP/Microsoft/MSChart_for_3.5.exe)-instalační balik pro framework .NET 3.5 pro generovani grafu

[CLIDATA_GIS_ALL_LAST.zip](http://192.168.90.66/kwapplications/GIS/Apps/ZIP/CLIDATA_GIS_ALL_LAST.zip) -kompletni poslední verze instalační balík pro instalaci klienta ClidataGIS

na nové PC

**INSTALL_DIR** je instalační adresář, kde jsou všechny staženy a odzipované dílčí aplikace

***
## Instalace na  PC bez předchozí instalace Clidata GIS

Novou instalaci ClidataGIS na PC bez předchozí instalace je dle tohoto postupu:  

Instalace aplikací doporučuji přes příkazový řádek (cmd.exe) spustěný jako administrátor.
Jelikož se během instalace budou zapisovat některé údaje do registru OS je potřeba instalaci dělat pod daným uživatelem(ideálně uživatel s dočasnými administrátorskými právy)  

**PK,MW** - potřeba pro aplikaci plošná kontrola (**PK**) a pro MapViewer (**MW**)  
**SA** - potřeba pro aplikaci prostorové analýzy pod ArcGIS

1. Instalace Oracle clienta **PK,MW,SA** INSTALL_DIR\Oracle\install_oracleClient.cmd 
2. Instalace DotNet 4.5 pokud již není nainstalovavý v systému  **_PK,MW,SA INSTALL_DIR\dotNet45.exe**
3. Instalace ArcGIS 10.6.1 **SA** pokud tato verze je již instalovaná na PC tak přeskočit tento krok
**INSTALL_DIR/ArcGIS_Desktop_106_161544.exe**
4. Instalace ArcGIS Explorer 3400 s volbou Anyone who uses this computer (all Users)  !!!!! **PK,MW**    
**INSTALL_DIR\ESRI/ArcGIS Explorer 3400\Setup.exe**
5. Instalace ArcGIS Explorer Fonts  
6. **INSTALL_DIR\ESRI/ArcGISExplorerFonts\Setup.exe**
7. Instalace aplikace ClidataGIS  **PK,MW,SA**  
**Odzipování CLIDATA_GIS_LAST.zip do C:\ClidataGIS**
8. Vytvoření zástupce na ploše s cestou  
   **C:\ClidataGIS\ClidataGIS_Starter.exe CHMU.xml**
9.  Registrace ClidataGIS do ArcMap  **SA**  
    
    C:\ClidataGIS\BIN\Registry_ClidataGIS10.6.cmd_ pro verzi 10.6  
    C:\ClidataGIS\BIN\Registry_ClidataGIS10.7.cmd_ pro verzi 10.7 
    C:\ClidataGIS\BIN\Registry_ClidataGIS10.8.cmd_ pro verzi 10.8  
***
## Instalace na PC s předchozí verzi Clidata GIS

Pokud na PC již existovala předchozí verze ClidataGIS je potřeba před samotnou instalaci: 
1. Odinstalovat ArcGIS 10.3 a nižší verze
2. Odinstalovat ArcGIS Explorer
4. Smazat složku ClidataGIS10
5. Restart PC
6. Pokračovat v instalaci jako ve verzi bez předchozí instalace ClidataGIS

***

## Řešení problému

**Nedaří se se spustit ArcGIS Explorer z menu ClidataGIS a máte 32bit operační systém?**

je potřeba modifikovat soubor C:\ClidataGIS\chmu.xml a parametr *arcExplorer* C:\Program Files (x86)\Explorer (x86)\bin\e3.exe  
upravit na skutečnou cestu, kde je e3.exe soubor (ArcGIS Explorer)  

**Registrace extenze ClidataGIS do aplikace ArcGIS 10.5**

Knihovna Striz.AG10.4.dll je kompilovaná pro verzi ArcGIS 10.4 a k registraci používá program esriRegasm.exe,který je ve složce C:\ClidataGIS\BIN\ESRI. Pokud máte na PC nainstalovanou vyšší verzi ArcGIS např. 10.5 je potřeba pro registraci spustit soubor esriRegams.exe pro verzi 10.5
z adresáře 
C:\Program Files (x86)\Common Files\ArcGIS\bin s parametrem Striz.AG10.4.dll /p:Desktop

**Instalace .NET FrameWork 3.5 do Windows 10**

Windows 10. Install .NET Framework 3.5 error 0x800F0954

1. V registrech ve složce HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU nastavit “UseWUServer” na 0 	
2. Restart 	počítače
3. Instalace .NET Framework 3.5 
4. V registrech ve složce **KEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU** nastavit zpět hodnotu **UseWUServer** na 1	
5. Restartovat počítač 	