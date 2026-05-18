All contents within this file are subject to change.

Setting up the Windows 11 + Splunk Forwarder VM.
	A) Get a Windows 11 ISO from the official Microsoft website. https://www.microsoft.com/en-us/software-download/windows11
	B) Create a VM in Oracle VirtualBox using the ISO you downloaded.
	C) Download the Splunk Forwarder .msi for Windows 11. https://www.splunk.com/en_us/download/universal-forwarder.html
	D) Complete the installation by following the GUI's instructions and go to This PC > Windows (C:) > Program Files > Splunk Universal Forwarder > etc > system > local.
	E) Open inputs.conf with notepad and make sure that the following are in it:
	
		[WinEventLog://Security]
		disabled = 0
		
		[WinEventLog://System]
		disabled = 0
		
		[WinEventLog://Application]
		disabled = 0
		
	F) Then, open outputs.conf with notepad and make sure that the following are in it: 
	
		[tcpout]
		defaultGroup = default-autolb-group
		
		[tcpout:default-autolb-group]
		server = <VM-IP>:9997
		
	G) Go to your Splunk Web Interface > Settings > Forwarding and receiving > Configure receiving > New Receiving Port > 9997.
