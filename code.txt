cls
@ECHO OFF
title Vault
if EXIST "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" goto UNLOCK
if NOT EXIST Vault goto MDVault
:CONFIRM
echo Are you sure u wanna Lock the Vault ??   (Y/N)
set/p "cho=>"
if %cho%==Y goto LOCK
if %cho%==y goto LOCK
if %cho%==n goto END
if %cho%==N goto END
echo Invalid choice.
pause
goto CONFIRM
:LOCK
ren Vault "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
attrib +h +s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
echo Vault locked
goto End
:UNLOCK
echo  Welcome to the Vault...
echo[
echo  This is a secret facility of Aditya
echo[
echo  Plz enter the Password:
set/p "pass=>"
if NOT %pass%== password goto FAIL
attrib -h -s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"
ren "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" Vault
echo Vault Unlocked successfully
goto End
:FAIL
cls
echo[
echo  INVALID PASSWORD
echo[
echo  You are not Aditya
echo[
echo  Plz do not intrude into his privacy
echo  You can rather ask if you want something
echo  :)
echo[
echo[
echo[
echo[
pause
goto end
:MDVault
md Vault
echo Vault created successfully
pause
goto End
:End