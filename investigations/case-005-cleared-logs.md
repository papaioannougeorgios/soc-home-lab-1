A log clearing attempt was observed on the Windows VM. The activity was detected through the ingested Windows Security Logs into Splunk SIEM..

Attack Details

	Attack Type: Log Clearing Attempt
	Attack Result: Successful
	Source: Localhost (127.0.0.1) - attack from the same endpoint.
	Event Code: 1102
	Log Source: Windows Security Event Logs
	Analysis Platform: Splunk SIEM

Timeline

	18/05/2026, 05:43:18.735 PM

Security Measures

	Restrict permission to clear logs to admins only.
	Alert immediately on Event Code 1102.
	Enable log integrity monitoring.

Detection Logic (Splunk SPL)

	index=* EventCode=1102 | table _time, Account_Name, host, Message

Conclusion

	The audit log was successfully cleared, this was a simulated attack.

Log screenshots included in detections/ folder.
