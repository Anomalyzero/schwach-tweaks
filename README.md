# schwach-tweaks
Docs, notes &amp; scripts on tweaks I often like to apply to my machines

## Windows

### Show Seconds on System Clock
[Source](https://www.howtogeek.com/325096/how-to-make-windows-10s-taskbar-clock-display-seconds/)
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
