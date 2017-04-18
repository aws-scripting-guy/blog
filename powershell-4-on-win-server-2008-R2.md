# PowerShell 4.0 on Windows Server 2008 R2

If you still have Windows 2008 R2 you can install PowerShell 4.0 on it.

PowerShell 4 is part of Windows Management Framework 4 (WMF 4). There's a [known issue](https://blogs.msdn.microsoft.com/powershell/2013/10/28/wmf-4-0-known-issue-partial-installation-without-net-framework-4-5/) that WMF installer will not check all prerequisites are installed, 
will continue to install and leave PS installation corrupt.

***NET 4.5 needs to be installed before installing WMF 4.0.***

If you installed WMF 4.0 first (like I did) you can rollback and follow up procedure below to fix.

This worked for me:

1. Uninstall all KBs which are part of WMF 4.0 (you can find them listed here)
2. Install NET. 4.5
3. Install WMF 4.0
4. Enjoy PoweShell 4

That's it. Now you can get back to 2013 with Win 2008 R2.
