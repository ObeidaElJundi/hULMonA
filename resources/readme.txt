How many lines in a particular file: (Windows Powershell)
Get-content .\samples\output\all_arabic_wiki_2019.txt.MyD3.tok | Measure-Object –Line

Copy first 100 lines from one file to another: (Windows Powershell)
Get-Content -First 100 .\samples\output\all_arabic_wiki_2019.txt.MyD3.tok -Encoding UTF8 | Out-File .\samples\output\100sample.txt -Encoding UTF8

Run MADAMIRA: (make sure you are using JDK 64 not 32)
C:\Users\oae15\Downloads\JDK64\bin\java.exe -Xmx3000m -Xms3000m -XX:NewRatio=3 -jar MADAMIRA-release-20170403-2.1.jar -rawinput "C:\Python\Python36\coding4fun\Notebooks\fastai\for research\Ar_LM\data\ASTD_text_only.txt" -rawoutdir .\samples\output -rawconfig .\samples\sampleConfigFile.xml -msaonly