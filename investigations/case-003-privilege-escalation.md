A user privilege escalation was observed on the Windows VM. The activity was detected through the ingested Windows Security Logs into Splunk SIEM.

Attack Details

	Attack Type: User Privilege Escalation (Local Group Change)
	Attack Result: Successful
	Source: Localhost (127.0.0.1) - attack from the same endpoint.
	Event Code: 4732
	Log Source: Windows Security Event Logs
	Analysis Platform: Splunk SIEM

Timeline

	18/05/2026, 05:37:57.885 PM

Security Measures

	Apply PoLP.
	Remove users from local admin group by default.
	Enable PAM.
	Enable audit policies for group membership changes.

Detection Logic (Splunk SPL)

index=* EventCode=4732 | stats count by SubjectUserName, TargetUserName, Group_Name

Conclusion

	The user's (SID: S-1-5-21-2271620164-1335179883-2486912170-1001) group was successfully escalated to "Administrators", this was a simulated attack.

Log screenshots included in detections/ folder.
