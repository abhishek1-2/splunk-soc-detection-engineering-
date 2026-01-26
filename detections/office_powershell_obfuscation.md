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
Severity is Medium, indicating suspicious behavior with potential impact but insufficient confidence to escalate immediately.

## Response 

Assign to SOC analyst for investigation, review recent document activity, and monitor the host for additional suspicious behavior.

## Suppression  
Server hosts excluded.  

## Review defense 
Microsoft office do not launch the Powershell in normal ser work da flows , makes this parent-chid realtion rear and indicate malicious document execution . The uses of obfucation is observerd in Powershell , increses the confidense . Noise can be  controlled by the exclusion of the server host . The analyst should investigate the recent activity of the host and reviwe the perivious documents of the host . 
