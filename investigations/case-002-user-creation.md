A new user creation was observed on the Windows VM. The activity was detected through the ingested Windows Security Logs into Splunk SIEM.

Attack Details
	Attack Type: New User Creation
	Attack Result: Successful
	Source: Localhost (127.0.0.1) - attack from the same endpoint.
	Event Code: 4720
	Log Source: Windows Security Event Logs
	Analysis Platform: Splunk SIEM

Timeline
	18/05/2026, 05:34:43.589 PM

Security Measures
	Restrict user creation to admin-only groups.
	Enable UAC hardening.
	Audit all new account creations via SIEM alerts.
	Disable unused local accounts.

Detection Logic (Splunk SPL)
	index=* EventCode=4625 | table _time, Account_Name, TargetUserName, host

Conclusion
	A new user was successfully created on the target under the account name "soc_test_user", this was a simulated attack.

Log screenshots included in detections/ folder.
