# How to Find and Catalog files

1. Make a folder in C:\ called "diskcatalog" or similar
2. Go to the root of your C drive, and open a command prompt (not powershell)
3. Use these commands:
````
chcp 65001
dir /s >DRIVE_NAME.txt
````
chcp changes the codepage to unicode. Important if you have some foreign-named files. /s means recursive. optionally add /b if you just want filenames, not mod-date & filesize. substitute DRIVE_NAME for a sensible filename.
4. Repeat steps 2-3 for every drive