# schwach-tweaks
Docs, notes &amp; scripts on tweaks I often like to apply to my machines

## Windows

### Show Seconds on System Clock
```pwsh
$RegPath='HKCU:\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced'
$RegPropName='ShowSecondsInSystemClock'
$RegPropValue='1'

# Create the key if it does not exist
If (-NOT (Test-Path $RegPath)) {
  New-Item -Path $RegPath -Force | Out-Null
}

# Now set the value
New-ItemProperty -Path $RegPath -Name $RegPropName -Value $RegPropValue -PropertyType DWORD -Force
```
- [Show Seconds Registry Source](https://www.howtogeek.com/325096/how-to-make-windows-10s-taskbar-clock-display-seconds/)
- [PWSH Set Reg Values Source](https://devblogs.microsoft.com/powershell-community/how-to-update-or-add-a-registry-key-value-with-powershell/)
