# Mic2Paper
An easy to use python script that collects entropy through the microphone and generates a printable paper wallet.

### Installation
Install git, python3 and pip (if needed):
```
sudo apt install git python3 python3-pip
```
Clone the repository:
```
git clone https://github.com/ASeriousMister/Mic2Paper
```
Move to the tool's directory
```
cd /path/Mic2Paper
```
Install requirements (read above for Python virtual envitonments):
```
pip3 install -r requirements.txt
```
Additional resources, needed to generate printable pdf files:
```
sudo apt install wkhtmltopdf
```
for Windows install [WKHTMLTOPDF](https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.4/wkhtmltox-0.12.4_msvc2015-win64.exe)

Run the tool:
```
python3 mic2paper.py
```

### Utilization
User simply has to start the tool and wait until it collects entropy.
At the end, the tool will show private keys and public addresses and, if wanted, generates a printable paper wallet in the PaperWallet directory.
If user does not want to generate the printable paper wallet, keys are not stored anywhere.
QrCodes of the information can also be obtained with tools like qrencode or QtQR.

### Supported coins
The tools supports the following coins, to add more simply edit the code referring to hdwallet documentation for the correct symbols
- Bitcoin
- Ethereum
- Litecoin
- Bitcoin Cash
- Bitcoin SV
- Dash
- ZCash
- DogeCoin
- Bitcoin Testnet
- Monero

### Optional: using Virtual Environment
Install python virtual environments
```
pip3 install virtualenv
```
Now move to DiceTracker.py's directory,
```
cd Mic2Paper
```
create a virtual environment (in the example named dtve, but you can choose your preferred name)
```
virtualenv mpve
```
and activate it
```
source mpve/bin/activate
```
The name of the virtual enviroment should appear, in brackets, on the left of your command line. 
Now install the dependencies
```
pip3 install -r requirements.txt
```
Additional resources, needed to generate printable pdf files:
```
sudo apt install wkhtmltopdf
```
Finally, run the tool
```
python3 mic2paper.py
```

### Troubleshooting
The tool may encounter some issues running with recent Linux distros, due to incompatibility with ripemd160 hashes used by the hdwallet library.
To solve this you need to edit the /etc/ssl/openssl.cnf file, making sure that it contains all the following lines:
```
openssl_conf = openssl_init

[openssl_init]
providers = provider_sect

[provider_sect]
default = default_sect
legacy = legacy_sect

[default_sect]
activate = 1

[legacy_sect]
activate = 1
```
### Disclaimer
This ool comes with no guarantees. Do your own research about how this tool works and in general about how cryptocurrency keys work before using it.

### Credits & Donations
This tool is part of the [AnuBitux](https://anubitux.org) project. 
If you appreciate this work visit https://anubitux.org and consider making a donation
- BTC: 1AnUbiYpuFsGrc1JFxFCh5K9tXFd1BXPg
- XMR: 87PTU58siKNb3WWXcP4Hq4CmCb7kMQUsEiUWFT7SvvMMUqVw9XXFGrJZqmnGvuJLGtLoRuEqovTG4SWqkPr8YLopTSxZkkL

