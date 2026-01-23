# Office → PowerShell Obfuscation Detection

## Detection Purpose
Detect potential malicious Microsoft Office documents that launch PowerShell with obfuscated command-line arguments.

## Why This Matters
Microsoft Office applications do not normally execute PowerShell during standard user workflows. When this behavior is combined with obfuscation flags, it may indicate malicious document execution.

## Detection Logic
- Parent process is a Microsoft Office application (WINWORD.EXE, EXCEL.EXE, POWERPNT.EXE)
- Child process is powershell.exe
- Command line contains obfuscation indicators such as -enc, -nop, or -w hidden

## Status
Detection logic documented. SPL implementation and tuning will be added incrementally.

