A brute force login attempt was initiated on the Windows VM using repeated authentication failures against multiple usernames. The activity was detected through the ingested Windows Security Logs into Splunk SIEM.

Attack Details

    Attack Type: Attempt to brute force login credentials.
	Attack Result: Unsuccessful
	Source: Localhost (127.0.0.1) - attack from the same endpoint.
	Event Code: 4625
	Log Source: Windows Security Event Logs
	Analysis Platform: Splunk SIEM

Timeline

	Start: 18/05/2026, 05:02:16.720 PM
	End: 18/05/2026, 05:02:37.291 PM

Security Measures

	Enable account lockout policy.
	Implement password complexity requirements.
	Enable MFA (Multi-Factor Authentication).
	Use fail2ban-like rate limiting logic (via Windows policies).
	
Detection Logic (Splunk SPL)

	index=* EventCode=4625 | stats count by Account_Name,src_ip | where count > 5

Conclusion

	No account was compromised, this was a simulated attack.

Log screenshots included in detections/ folder.
