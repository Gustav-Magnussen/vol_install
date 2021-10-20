# Volatility Install
Install guide for Volatility 2.6.1 on Linux.
## Install script
In order to install using the install script download and execute the [vol_install](https://raw.githubusercontent.com/Gustav-Magnussen/vol_install/main/vol_install?token=AOH75QDBYVDSCMENKFBRZADBN7PYQ) as sudo:
```
sudo ./vol_install
```

## Manual Install
Manual install guide.

### Python
Ensure that your system has python 2 installed:
```
$ python --version
$ Python 2.7.18
```

Install pip2 for python:
``` 
$ sudo apt update
$ curl https://bootstrap.pypa.io/pip/2.7/get-pip.py --output get-pip.py
$ sudo python2 get-pip.py
```

### Dependencies for Volatility 
#### Distorm3 and Pycrypto
Install dependencies:
```
$ sudo apt install python-setuptools build-essential python2-dev
$ sudo pip2 install distorm3==3.3.4
$ sudo apt-get install yara -y
$ wget https://ftp.dlitz.net/pub/dlitz/crypto/pycrypto/pycrypto-2.6.1.tar.gz
$ tar -xvzf pycrypto-2.6.1.tar.gz
$ cd pycrypto-2.6.1
$ python2 setup.py build
$ sudo python2 setup.py build install
```

### Volatility
Install volatility:
```
$ sudo apt install git
$ git clone https://github.com/volatilityfoundation/volatility.git
$ chmod +x volatility/vol.py
```

If you want to move install to /opt and make it globally executable:
```
$ sudo mv volatility /opt
$ sudo ln -s /opt/volatility/vol.py /usr/bin/vol.py
```

Run in order to test volatility.
```
$ vol.py -h
```
If this command returns the help page of volatility and volatility plugins you are ready to analyse volatile memory.

## Import errors
If you get an import problem with distorm3 like:
```
*** Failed to import volatility.plugins.mac.check_syscall_shadow (ImportError: No module named distorm3)
```

Install distorm3 in this manner:
```
$ wget https://github.com/gdabah/distorm/archive/refs/tags/v3.3.4.tar.gz
$ tar -xvzf v3.3.4.tar.gz
$ cd v3.3.4
$ python2 setup.py build
$ python2 setup.py build install
```


