# vol_install
Install guide for Volatility 2.6.1 on Linux.


## Python
Ensure that your system has python 2 installed:
'''
$python --version
Python 2.7.18
'''

Install pip2 for python:
''' 
sudo apt update
curl https://bootstrap.pypa.io/pip/2.7/get-pip.py --output get-pip.py
sudo python2 get-pip.py
'''

## Dependencies for Volatility 
### Distorm3 and Pycrypto
Install dependencies:
'''
sudo apt install python-setuptools build-essential python2-dev
sudo pip2 install distorm3==3.3.4
sudo apt-get install yara -y
wget https://ftp.dlitz.net/pub/dlitz/crypto/pycrypto/pycrypto-2.6.1.tar.gz
tar -xvzf pycrypto-2.6.1.tar.gz
cd pycrypto-2.6.1
python2 setup.py build
sudo python2 setup.py build install
'''

## Volatility
Install volatility:
'''
sudo apt install git
git clone https://github.com/volatilityfoundation/volatility.git
chmod +x volatility/vol.py
'''

Move install to /opt and make it globally executable:
'''
sudo mv volatility /opt
sudo ln -s /opt/volatility/vol.py /usr/bin/vol.py
'''


