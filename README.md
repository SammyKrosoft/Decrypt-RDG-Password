# Decrypt-RDG-Password
Load RDCMan.exe as PowerShell module - Trick by Thomas PRUD'HOMME

This trick is from the great [Thomas Prud'homme](https://blog.prudhomme.wtf/author/thomas/) he published back in 2016 but still working in 2022 with the latest version of RDCMan.exe ([Remote Desktop Connection Manager](https://learn.microsoft.com/en-us/sysinternals/downloads/rdcman)).

The below code helps recoding the password stored in your RDG file, using RDCMan.exe as a PowerShell module.

```powershell

Copy-Item 'C:\Program Files (x86)\Microsoft\Remote Desktop Connection Manager\RDCMan.exe' 'C:\temp\RDCMan.dll'

Import-Module 'C:\temp\RDCMan.dll'

$EncryptionSettings = New-Object -TypeName RdcMan.EncryptionSettings

[RdcMan.Encryption]::DecryptString($PwdString, $EncryptionSettings)

```

The original post is [here](https://blog.prudhomme.wtf/2016/03/16/use-powershell-to-decrypt-password-stored-in-a-rdg-file/)

Thanks Thomas !
