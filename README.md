Look up word in Dictionary and log it on desktop (LookupLog.txt) using ActionScript.


```
on run {input, parameters}
	
	open location "dict://" & input
	
	set logFile to "LookupLog.txt"
	set logPath to quoted form of (POSIX path of (path to desktop folder as string) & logFile)
	set timeStamp to do shell script "date +%Y-%m-%d"
	do shell script "echo " & timeStamp & " \" : " & input & "\" >> " & logPath
	return input
	
end run

```
