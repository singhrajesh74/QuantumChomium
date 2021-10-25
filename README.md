# QuantumChomium
Open Quantum Safe Chromium Browsers

I created this to help test Open Quantum Safe Cryptograhy.
<br>The main Github for this project is here: https://github.com/open-quantum-safe/oqs-demos
<br>If you wanted a pre-built OQS Browser, get it here:
- Ubuntu: https://github.com/open-quantum-safe/oqs-demos/releases/download/v0.4.0/chromium-ubuntu-0.4.0.tgz
- Windows: https://github.com/andrew-nash/oqs-demos/releases/download/v0.1-alpha/windows-release.zip

To build your own Chromium browser:
1. Build a Ubuntu Server with 100GB free.
2. *sudo upgrade*
3. *sudo update*
4. *reboot*
5. *sudo visudo*
<br>Then change the timeout value. For example :
<br> *Defaults timestamp_timeout=360*
6. Open browser and go to: https://github.com/open-quantum-safe/oqs-demos.git
7. Click Code -> Download ZIP -> Save to Downloads directory
8. *cd /home/rsingh9/Downloads*
9. *unzip oqs-demos-main.zip*
10. *cd oqs-demos-main/chromium/scripts/*
11. *export PROJECT=/home/rsingh9/pqc_chromium*
12. *./master.sh*
13. Start chrome: *nohup /home/rsingh9/pqc_chromium/src/out/Default/chrome&*
