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

## SPL Query

The SPL query used to implement this detection is available here:

[spl/office_powershell_obfuscation.spl](../spl/office_powershell_obfuscation.spl)

## Severity 
Serverity is meadium , suspicious beheaviour with potential impact but insufficent confidens to escalte immedieatily .

## Response 

Assgin to soc analyst for investigation , review recent document , activity , monitor for host for additional  suspicious behavior .

## Suppression  
Server host excluded.  
