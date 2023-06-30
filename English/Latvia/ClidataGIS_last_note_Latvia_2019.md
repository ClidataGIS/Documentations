<!-- Copy and paste the converted output. -->

<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 2.186 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β29
* Sun Sep 13 2020 06:54:27 GMT-0700 (PDT)
* Source doc: ClidataGIS  for Latvia -last notes
* Tables are currently converted to HTML tables.
----->


# CLIDATA  advanced training GIS last notes

Ing. Martin Stříž 	(martin@striz.info)                                                   08. 03. 2019

**Term of training**:    25. 2. 2019 - 8. 2. 2019

**Place of training**:   Latvijas Vides, Geologijas Un Meteorologigijas Centrs, Riga


## **Clidata server connection**

 defined in c:\ClidataGIS\concfg.xml

&lt;?xml version="1.0" encoding="UTF-8" ?> 

&lt;config>

&lt;connection>

&lt;id>Clidata&lt;/id> 

&lt;displayName>Clidata&lt;/displayName> 

&lt;cstring>jdbc:oracle:thin:@(description=(address_list=(address=(host=212.70.174.82)(protocol=tcp)(port=1521)) )(connect_data=(service_name=CLIDATA)))&lt;/cstring>

&lt;/connection>

&lt;/config>

       


## **Spatial domain information**

**Area Control**

Coordinates system:  WGS84

GEOGCS["GCS_WGS_1984",DATUM["D_WGS_1984",SPHEROID["WGS_1984",6378137.0,298.257223563]],PRIMEM["Greenwich",0.0],UNIT["Degree",0.0174532925199433]]

**GIS Layers**:

	Robeza.shp - border country layer

            Novadi.shp  - regions layer

            Upes.shp - rivers layer

            Uzeri.shp - lakes layer

**Radar images**:

            Source folder: P:\RADAR_IMAGE\@YYYY\@MM\@YYYY@MM@DD.png

                                  example for 01.01.2019 radar image which is correlated to 01.01.2019 daily sum of precipitation is:   P:\RADAR_IMAGE\2019\01\20190101.png

Radar images are transform into AreaControl projection by 1st order polynomial (Affine) transformation with  these coefficients:

0,0031933118307479291

-6,3941004163946387e-006

1,0989911471409765e-006

-0,0024619724829289349

18,064482962390894

60,317834270920159

**MapViewer**

Coordinates system:  WGS84

GEOGCS["GCS_WGS_1984",DATUM["D_WGS_1984",SPHEROID["WGS_1984",6378137.0,298.257223563]],PRIMEM["Greenwich",0.0],UNIT["Degree",0.0174532925199433]]

**GIS Layers**:

	Robeza.shp - border country layer

            Novadi.shp  - regions layer

            Upes.shp - rivers layer

            Uzeri.shp - lakes layer

            dem.asc  - digital elevation model 

		     -resolution 0.0030041415563013 degrees (~ 240m)

**ClidataGIS for ArcGIS**

Coordinates system:  LKS_1992

PROJCS["LKS_1992_Latvia_TM",GEOGCS["GCS_LKS_1992",DATUM["D_Latvia_1992",SPHEROID["GRS_1980",6378137.0,298.257222101]],PRIMEM["Greenwich",0.0],UNIT["Degree",0.0174532925199433]],PROJECTION["Transverse_Mercator"],PARAMETER["False_Easting",500000.0],PARAMETER["False_Northing",-6000000.0],PARAMETER["Central_Meridian",24.0],PARAMETER["Scale_Factor",0.9996],PARAMETER["Latitude_Of_Origin",0.0],UNIT["Meter",1.0]]

**GIS Layers**:

	Robeza.shp - border country layer

            Novadi.shp  - regions layer

            Upes.shp - rivers layer

            Uzeri.shp - lakes layer

            dem.asc  - digital elevation model extent of Latvia

		     -resolution 240m

            demBig.asc-digital elevation model with extent over border of Latvia

                            -resolution 240m

 **Standard DEM** is set to dem.asc, by tool Set terrain in Setting menu of ClidataGIS toolbar in ArcGIS, you can temporary set bigger one (demBig.asc) for interpolation over border of Latvia.

**Standard map templat**e : C:\ClidataGIS\AG\LV\templates\template_LV.mxd for ArcGIS version 10.4 ,10.5,10.6

For older 10.3 version of ArcGIS template is C:\ClidataGIS\AG\LV\templates\template_LV10.3.mxd

**Console utils:**

Folder \\USB\ClidataGIS_BIN

**SQL2CSV.exe** for downloading data from Clidata db to CSV text file

**LLR2ASC.exe** for interpolate input data in CSV file to raster Ascii file (*.asc)

**MapGenerator.exe** for creating map with (title,legend,logo) from raster *.asc into image file *.png


## Installation ClidataGIS


### Installation on new (without previous installation of ClidataGIS) 

Clidata GIS installation progress install these programs:



*   **Oracle client for .NET framework**
*   **Microsoft .NET 3.5 framework**
*   **Microsoft .NET 4 framework**
*   **MSChart library for .NET**
*   **ArcGIS Explorer 3400**
*   **Google Earth** (optional)
*   **Clidata GIS client**

Due to possible problems with users operation system rights I recommend to use **CMD.exe** (**run as administrator**) to install all programs.

InstallDir mean installation directory for ClidataGIS (usually USB:\ClidataGIS_Install\Install.

Please follow these steps:



1. click on Start button in Windows desktop
2. click on run
3. type cmd
4. right mouse on cmd and choose run as administrator
5. in CMD.exe windows continue
6. go to InstallDir (using DOS commands like dir, cd etc)
7. then cd oracle
8. run install_oracleClient.cmd for install oracle instant client for .NET
9. wait for finish
10. then cd ..
11. cd .NET
12. run dotnetfx35.exe for install Microsoft .NET Framework 3.5
13. run dotnetFx40_full_x86_x64.exe for install Microsoft .NET Framework 4.0
14. run MsChart_for_3.5.exe for install Microsoft Chart library for .NET
15. cd ..
16. cd ArcGISExplorer 3400
17. run _Setup.exe_ for install ArcGIS Explorer version 3400
18. cd ..
19. cd ArcGISExplorerFonts
20. optionaly install Google Earth → from Google\googleearthwin-peruser.exe
21. install ClidataGIS by run clidataGIS_lx.exe where x mean Clidadata GIS level (l1,l2,l3)


### **Upgrade existing ClidataGIS**



1. Uninstall previous version of ClidataGIS
2. Install Oracle client for .NET Framework
3. Install ArcGIS Explorer version 3400
4. Install ClidataGIS client

Due to possible problems with users operation system rights I recommend to use **CMD.exe** (**run as administrator**) to install all programs.

InstallDir mean installation directory for ClidataGIS (usually USB:\GIS\Install.

Please follow these steps:



1. click on Start button in Windows desktop
2. click on run
3. type cmd
4. right mouse on cmd and choose run as administrator
5. in CMD.exe windows continue
6. go to InstallDir (using DOS commands like dir, cd etc)
7. then cd oracle
8. run install_oracleClient.cmd for install oracle instant client for .NET
9. wait for finish
10. then cd ..
11. cd .NET
12. cd ArcGISExplorer 3400
13. run _Setup.exe_ for install ArcGIS Explorer version 3400
14. cd ..
15. cd ArcGISExplorerFonts
16. optionaly install Google Earth → from Google\googleearthwin-peruser.exe
17. install ClidataGIS by run clidataGIS_lx.exe where x mean Clidadata GIS level (l1,l2,l3)


## Documentations

Documentation folder is C:\ClidataGIS\Doc   or on \\USB\ClidataGIS_Install\Doc


## Training schedule

Training was done according to this schedule


<table>
  <tr>
   <td>Version
   </td>
   <td>2.19.3.7
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>Day</strong>
   </td>
   <td><strong>WD</strong>
   </td>
   <td><strong>Plan</strong>
   </td>
   <td>
   </td>
   <td><strong>Who</strong>
   </td>
   <td>ArcGIS Single licence
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>25.2.2019</strong>
   </td>
   <td><strong>1</strong>
   </td>
   <td>Customization of Clidata GIS applications according to local database, network conditions
   </td>
   <td>
   </td>
   <td>M, IT
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Implementation of national GIS layer to Clidata GIS application
   </td>
   <td>
   </td>
   <td>M, GIS
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Connection to Clidata Server
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Prepare vector layers for AreaControl, convert it into ArcGIS Explorer format
   </td>
   <td>
   </td>
   <td>M, GIS
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Prepare vector layers for MapViewer, prepare raster (DEM) layer for MapViewer
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>26.2.2019</strong>
   </td>
   <td><strong>2</strong>
   </td>
   <td>Prepare vector layers for ClidataGIS for ArcMap
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Prepare raster layer for ClidataGIS for ArcMap
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Prepare ArcMap template with Latvian layers for ArcGIS
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td><strong>27.02.2019</strong>
   </td>
   <td>3
   </td>
   <td>Release new version of Clidata GIS with local setting
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Test application on one client PC
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Installation of Clidata GIS clients
   </td>
   <td>
   </td>
   <td>M,IT?
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Solving issues raised during installation
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>28.2.2019</strong>
   </td>
   <td><strong>4</strong>
   </td>
   <td>Quality Control in Clidata using GIS Area Control
   </td>
   <td>
   </td>
   <td>M,QC
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Definition of geography for Area Control
   </td>
   <td>
   </td>
   <td>M,QC
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Definition of element for Area Control
   </td>
   <td>
   </td>
   <td>M,QC
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Definition of extremes for Area Control
   </td>
   <td>
   </td>
   <td>M,QC
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>GIS Area Control Practise
   </td>
   <td>
   </td>
   <td>M,QC
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td><strong>1.3.2019</strong>
   </td>
   <td><strong>5</strong>
   </td>
   <td>Simple Map Viewer-getting daily data (RDATA)
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Simple Map Viewer-getting monthly data (MDATA)
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Simple Map Viewer-getting extreme data (EDATA)
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Simple Map Viewer-getting normal data (NDATA)
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Simple Map Viewer-interpolation station's data
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Simple Map Viewer-making isolines
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Simple Map Viewer-raster calculator
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Solving issues raised during training AreaControl Batch control optimizations
   </td>
   <td>
   </td>
   <td>M, QC
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td><strong>4.3.2019</strong>
   </td>
   <td>
   </td>
   <td>Getting started with ArcGIS application
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Open ArcMap, Save, Open Project
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Add shapeFile layer, Delete layer
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Data Selections, by mouse, by attribute, by location
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Exporting selection into new shapefile
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Symbolize layers, change color, mark etc
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Labeling layers
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Export map into Image File
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Import point data from Excel
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>5.3.2019</strong>
   </td>
   <td><strong>7</strong>
   </td>
   <td>How to add raster layer example of monthly TDRY temperature
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Export raster data (Erdas image, Ascii Grid)
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Interpolate point meteorological station into surface with IDW
   </td>
   <td>
   </td>
   <td>M, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Clidata GIS for ArcGIS
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>getting daily data (RDATA)
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>getting monthly data (MDATA)
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>getting extreme data (EDATA)
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>getting normal data (NDATA)
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>getting CSV data
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>getting data by SQL
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td><strong>6.3.2019</strong>
   </td>
   <td><strong>8</strong>
   </td>
   <td>Clidata GIS for ArcGIS
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Raster analysis- interpolation
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Raster analysis-area statistics
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Raster analysis-smoothing surface
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Raster analysis-raster calculator
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Raster analysis-make isolines
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>YES
   </td>
  </tr>
  <tr>
   <td><strong>7.3.2019</strong>
   </td>
   <td><strong>9</strong>
   </td>
   <td>Using GIS in Czech Hydrometeorological Institute (Web publish, GIS for customers,etc..)
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>MWLR application
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Principle of MWLR interpolation method
   </td>
   <td>
   </td>
   <td>M, GIS, GIS_b
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>ClidataGIS utils apps (SQL2CSV.EXE)
   </td>
   <td>
   </td>
   <td>M,GIS
   </td>
   <td>NO
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>ClidataGIS utils apps (LLR2ASC.EXE)
   </td>
   <td>
   </td>
   <td>M,GIS
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>ClidataGIS utils apps (MapGenerator.exe)
   </td>
   <td>
   </td>
   <td>M,GIS
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>08.03.2019</strong>
   </td>
   <td><strong>10</strong>
   </td>
   <td>Modify new radar image for using in AreaControl
   </td>
   <td>
   </td>
   <td>M,GIS
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Creation second DEM file is extent is over border of Latvia
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Finalization last installation package for ClidataGIS
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>Installation of last installation package on users PC
   </td>
   <td>
   </td>
   <td>M
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>Users:</strong>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>M
   </td>
   <td>
   </td>
   <td>Clidata GIS trainer
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>QC
   </td>
   <td>
   </td>
   <td>People who will work with AreaControl,usually Quality Control persons
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>GIS
   </td>
   <td>
   </td>
   <td>Persons with ArcGIS skills
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>GIS_b
   </td>
   <td>
   </td>
   <td>Persons without GIS knowledge
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
</table>
