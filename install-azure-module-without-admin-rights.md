# Install Azure module without admin rights

### Enable verbose as it might take some time and it might seem like nothing happens for a long time
```
Install-Module -Name AzureRM -Repository PSGallery -Force -Scope CurrentUser -verbose
```
