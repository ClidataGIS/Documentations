<!-- Copy and paste the converted output. -->

<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 0.526 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β29
* Sun Sep 13 2020 05:33:08 GMT-0700 (PDT)
* Source doc: ClidataGIS Level 1 Installation
----->



# **Installation of ClidataGIS Area Control**


## 2.18.11.15

Clidata GIS installation progress install these programs:



*   **Oracle client for .NET framework**
*   **Microsoft .NET 3.5 framework**
*   **Microsoft .NET 4 framework**
*   **MSChart library for .NET**
*   **ArcGIS Explorer 3400**
*   **Clidata GIS client**

Due to possible problems with users operation system rights I recommend to use **CMD.exe** (**run as administrator**) to install all programs.

InstallDir means installation directory for ClidataGIS (usually USB:\GIS\Install.

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
20. install ClidataGIS by run clidataGIS_L1.exe 
