# Network Mapper

Thanks Nancy for creating this. 

Run this from your terminal to map network drives drives.

Place code below in a file called `mapit.bat` and run from **CMD** or **PowerShell**.

```cmd

net use g: /d
net use i: /d
net use p: /d
net use r: /d
net use s: /d

rem Old Group
rem net use g: \\amcsdfs7071.amed.ds.army.mil\ameddcs\G_Drive /p:y  

rem Group
rem net use f: \\amcsdfs7071.amed.ds.army.mil\ameddcs\G_Drive /p:y  

rem Personal
# net use i: \\amcsdfs7071\ameddcs\I_Drive\<YOUR-USERID-HERE> /p:y   
# net use i: \\amcsdfs7071\ameddcs\I_Drive\frank.s.pigeon3 /p:y   

rem Production
net use p: \\amcsc20072\inetpub$ /p:y  				

rem Public
net use r: \\amcsc20043\inetpub$ /p:y  				

rem OldStuff
rem net use s: \\amcsc27048\inetpub$ /p:y			

rem Staging
net use s: \\139.232.7.48\inetpub$\HRCE /p:y		

```