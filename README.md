# schwach-tweaks
Docs, notes &amp; scripts on tweaks I often apply to machines

## Windows 10 Only

### Show Seconds on System Clock
***NOTE: This does not take effect until the user fully signs out and back in***
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
