#Windows 備份指令指南

本說明適用於Micorsoft Windows系統，使用基本的SHELL指令，而非POWER SHELL指令

指令詳細可參考[Win32 Shell Scripting Tutorial](http://www.csie.ntu.edu.tw/~r92092/ref/win32/win32scripting.html#Win32Scripting-Variables "Win32 Shell Scripting Tutorial")

##基本指令

註解（不會被執行）

		REM 我是註解
		
任意按鍵繼續

		PAUSE

關閉指令顯示

		echo off		

清除螢幕

		cls

停止程式

		taskkill /IM 執行檔名稱

顯示訊息

		echo 訊息

等待幾秒（這個有的系統可以有的不行）

		timeout /t 秒數
##變數

設定變數

		set 變數名稱=值

取出變數

		echo %變數名稱%

例如用於設定壓縮檔案名稱

		set FileName=backup%date:~0,4%%date:~5,2%%date:~8,2%.7z
		7za a -t7z %FileName% *.txt
		
##複製檔案
		COPY "來源" "目標"

如果是複製資料夾則使用

		XCOPY /E /Y "來源" "目標"

如果要加上日期時間則在**目標**檔名中加上 
		
		%date:~0,4%%date:~5,2%%date:~8,2%				

##中斷網路芳鄰
		net use \\IP /delete

##掛載網路芳鄰

		net use Z: \\IP\資料夾 /user:使用者名稱 使用者密碼 

##7zip命令列版本

請下載Command Line版本
[下載頁面](http://www.7-zip.org/download.html "下載頁面")

壓縮檔案指令

		7za a -t7z 壓縮產出檔案 要壓縮的檔案
		7za a -t7z files.7z *.txt

加上日期時間

		7za a -t7z files%date:~0,4%%date:~5,2%%date:~8,2%.7z *.txt