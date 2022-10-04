# b4x22021004
B4X實驗: 用wkhtmltopdf將HTML轉成(產生)PDF報表格式,(B4J)
B4X實驗: 用wkhtmltopdf將HTML轉成(產生)PDF報表格式,(B4J)
參考資料:
https://www.b4x.com/android/forum/threads/generate-pdf-reports-using-html-template-engine-json-data-in-b4j.129724/#content
https://segmentfault.com/a/1190000018988358


0.下載點
https://wkhtmltopdf.org/downloads.html

1.linux安裝軟體 
http://www.ptbird.cn/wkhtmltopdf-html-to-pdf.html

sudo apt-get install openssl build-essential xorg libssl-dev libxrender-dev
sudo apt-get install wkhtmltopdf 

2.使用
wkhtmltopdf [GLOBAL OPTION]... [OBJECT]... <output file>

"C:\Program Files\wkhtmltopdf\bin\wkhtmltopdf" https://www.baidu.com 1.pdf

wkhtmltopdf --footer-center  " [page] of [topage] " https://google.com/  1.pdf



3.批次檔方式toPdf.bat
echo "wkhtmltopdf [GLOBAL OPTION]... [OBJECT]... <output file>"

set wkDIR= "C:\Program Files\wkhtmltopdf"

set GLOBAL_OPTION= --footer-center  "My Text"
set OBJECT= https://www.google.com
set output_File= "E:\1.PDF"

set STARTDIR= "E:\"



cd %STARTDIR%

%wkDIR%\bin\wkhtmltopdf %GLOBAL_OPTION% %OBJECT% %output_File%

PAUSE

4.頁首/頁尾
https://www.mugo.ca/Blog/Generate-highly-customized-PDFs-with-wkhtmltopdf-and-eZ-Publish

頁眉和頁腳：
頁眉和頁腳可以使用參數 --header-* 和 --footer-* 添加到文檔中。
有些參數也需要提供一個字元串 text 作為參數值。例如：--header-left
可以在 text 中使用以下變數，將會把以下變數替換為對應的值。

* [page]       當前正在列印的頁面的頁碼
* [frompage]   列印的第一頁的頁碼
* [topage]     列印的最後一頁的頁碼
* [webpage]    當前正在列印的頁面的 URL
* [section]    當前正在列印的章節的名稱
* [subsection] 當前正在列印的分段的名稱
* [date]       本地系統格式的當前日期
* [isodate]    ISO 8601 擴展格式的當前日期
* [time]       本地系統格式的當前時間
* [title]      當前頁對象的標題
* [doctitle]   輸出文檔的標題
* [sitepage]   當前正在處理的對象中當前頁面的頁碼
* [sitepages]  當前正在處理的對象中的總頁數

舉個例子：
--header-right "Page [page] of [toPage]"，
https://github.com/eric19740521/b4x22021004

 



