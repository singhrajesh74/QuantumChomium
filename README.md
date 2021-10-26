# Open Quantum Safe Chomium Build
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
<br> *Defaults timestamp_timeout=3600*
6. Open browser and go to: https://github.com/open-quantum-safe/oqs-demos.git
7. Click Code -> Download ZIP -> Save to Downloads directory
8. *unzip /home/rsingh9/Downloads/oqs-demos-main.zip*
9. *cd /home/rsingh9/Downloads/oqs-demos-main/chromium/scripts/*
10. Edit build_options.sh, so it looks like this:
<br>*#!/bin/bash
<br>  cd $CHROMIUM_ROOT
<br>  rm -f out/Default/args.gn
<br>  mkdir -p out/Default
<br>  echo "enable_nacl=false" >> out/Default/args.gn
<br>  echo "use_debug_fission=false" >> out/Default/args.gn
<br>  echo "is_clang=false" >> out/Default/args.gn
<br>  echo "blink_symbol_level=0" >> out/Default/args.gn
<br>  #echo "CCACHE_BASEDIR=/home/ubuntu" >> out/Default/args.gn
<br>  echo "is_debug=false" >> out/Default/args.gn
<br>  echo "symbol_level=0" >> out/Default/args.gn
<br>  gn gen out/Default*

13. *export PROJECT=/home/rsingh9/pqc_chromium*
14. *./master.sh*
15. Start chrome: *nohup /home/rsingh9/pqc_chromium/src/out/Default/chrome&*
16. Save Chrome to a tar file for reuse elsewhere
<br>*cd /home/rsingh9/pqc_chromium/src/out/Default
<br>tar -cvzf pqc_chromium.tar.gz --exclude='obj/*' --exclude='gen/*' --exclude=v8_context_snapshot_generator --exclude=mksnapshot --exclude=make_top_domain_list_variables --exclude=toolchain.ninja --exclude='\*\_\_pycache\_\_\*' .*
