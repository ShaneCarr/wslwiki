
# Verify you are running on Windows build 21364+
From a Windows command prompt, type _ver_ to verify which build you are running.
# wsl not starting

# narrow down problem
```bash
wsl  or wsl -v times out
```

## cfg controlflow guard
With the following instructions:

check if this is running: net start vmcompute

1, Open "Window Security"
2, Open "App & Browser control"
3, Click "Exploit protection settings" at the bottom
4, Switch to "Program settings" tab
5, Locate "C:\WINDOWS\System32\vmcompute.exe" in the list and expand it
6, Click "Edit"
7, Scroll down to "Code flow guard (CFG)" and uncheck "Override system settings"
8, Start vmcompute from powershell "net start vmcompute"


## restarting reinstall
Get-Service -Name 'Host Network Service' | Restart-Service
Get-Service LxssManager | Restart-Service


Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
Stop-Service -Name "com.docker.service"
wsl --unregister docker-desktop