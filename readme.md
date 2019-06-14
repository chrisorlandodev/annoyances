
Bit by case-insentive filenames on Windows when deploying to Linux? Run this as administrator in PowerShell in your source directory.

(Get-ChildItem -Recurse -Directory).FullName | ForEach-Object {if (-Not ($_ -like '*node_modules*')) { fsutil.exe file setCaseSensitiveInfo $_ enable } }
