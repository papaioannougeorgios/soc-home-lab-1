A service creation was observed on the Windows VM using. The activity was detected through the ingested Windows Security Logs into Splunk SIEM.

Attack Details
	Attack Type: Service Creation
	Attack Result: Successful
	Source: Localhost (127.0.0.1) - attack from the same endpoint.
	Event Code: 7045
	Log Source: Windows Security Event Logs
	Analysis Platform: Splunk SIEM

Timeline
	18/05/2026, 05:46:19.236 PM

Security Measures
	Restrict service creation to admins only.
	Whitelist known legitimate services.
	Use application allowlisting.
	Block execution from temp directories/user profile directories.

Detection Logic (Splunk SPL)
	index=* EventCode=7045 | table _time, Account_Name, Service_Name, Service_File_Name, host

Conclusion
	A new service was successfully created under the name "notepad.exe" at "C:\Windows\System32\", this was a simulated attack.

Log screenshots included in detections/ folder.
