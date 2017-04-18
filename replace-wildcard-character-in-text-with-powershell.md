# Replace wildcard (*) character in text with PowerShell

```
# I need to remove that star
$MyID = "AROA12334566778890:*
$MyID = $MyID -replace ":\*",""

# output
$MyID
AROA12334566778890
```
