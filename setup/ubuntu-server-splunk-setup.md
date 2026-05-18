All contents within this file are subject to change.

Setting up the Ubuntu Server + Splunk Enterprise VM.
	A) Get an Ubuntu Server ISO file through the official Ubuntu website. https://ubuntu.com/download/server
	B) Download Oracle VirtualBox and create the VM using the ISO you downloaded. https://www.virtualbox.org/wiki/Downloads
	C) Once you've logged in to the Ubuntu Server, download Splunk Enterprise by going to the linked website and cliking on "Linux" -> Copy wget link -> paste in your Ubuntu Server terminal. https://www.splunk.com/en_us/download.html
	D) Then, after finishing the installation, start splunk. When I did this project, you could start splunk with these commands: cd /splunk/bin \ sudo ./splunk start --run-as-root
	E) Wait until the web-server is available then run "ip a" on your terminal to get your VM's ip. Once you have it, go to your host machine's browser, and visit http://VM-IP:8000. Afterwards, log in with the credentials you were prompted to create.
