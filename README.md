# Invoke-Mimikatz

# Invoke-TokenManipulation
## Foreword
Heavily inspired by
- https://github.com/PowerShellMafia/PowerSploit/blob/master/Exfiltration/Invoke-Mimikatz.ps1

I changed some lines, as the original did not work properly.
## Changes
```
Before:  $GetProcAddress = $UnsafeNativeMethods.GetMethod('GetProcAddress') 
After:   $GetProcAddress = $UnsafeNativeMethods.GetMethod('GetProcAddress', [reflection.bindingflags] "Public,Static", $null, [System.Reflection.CallingConventions]::Any, @((New-Object System.Runtime.InteropServices.HandleRef).GetType(), [string]), $null);
```
