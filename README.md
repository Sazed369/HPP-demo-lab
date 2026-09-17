# W BANKING HPP-demo-lab

This is a deliberately vulnerable, local banking lab demonstrating OTP recipient parameter pollution. The lab is not tested for other vulnerabilities yet as its only purpose for now is to help demonstrate the mentioned vulnerability. The lab is only run in locally for safety reasons and the accounts used are only fictional. The vulnerability is intentional.

HTTP Parameter Pollution (HPP) is a vulnerability/attack technique where an attacker sends multiple values for the same HTTP parameter, exploiting the application's inconsistent handling of those values. In some cases, such as this one, If an application is vulnerable to this, an attacker can take over accounts without knowing the passwords, by knowing only the victim's email addresses.

# Dependancies
 
 The lab requires the following to run the web app efficiently:
 
 Python 3.10+
 Flask
 
# Setup

## After successfully setting up, read the Scenario at the end of this Readme to get the credentials and context of what's happening (story stuff).

Download the zip and extract the files to an empty folder, then open the terminal/cmd from the folder where you now have your files. Then run the following commands depending on which OS you are using.

### Linux/macOS

On your terminal, type the following commands in order:

```bash
python -m venv .venv
```
```bash
source .venv/bin/activate
```
```bash
pip install -r requirements.txt
```
```bash
python app.py
```
```bash
sudo nano /etc/hosts
```
Add this line inside the file:
```bash
127.0.0.1 banking.test
```
Once app.py is running (ensure that port 5000 is not in use), navigate to 
```bash 
http://banking.test:5000/ 
```

### Windows

```bash
python -m venv .venv
```
```bash
.venv\\Scripts\\activate
```
```bash
pip install -r requirements.txt
```
```bash
python app.py
```
Open C:\\Windows\\System32\\drivers\\etc\\hosts as administrator and add this line:
```bash
127.0.0.1 banking.test
```

Once app.py is running (ensure that port 5000 is not in use), navigate to 
```bash 
http://banking.test:5000/ 
```

# SCENARIO

W Banking is the most popular online banking app promising security and all that. Turns out its not all that, people have been losing their money, the trend is; most of the people whose accounts have been hacked are the ones whose registered emails are shared with the public and most claim that their passwords are very strong. You have been tasked with simulating how these accounts are being hacked in order to help W banking understand the danger better and how to protect their customers. You have been given the following credentials for your task.

 Disclaimer: The accounts used here are only fictional, no real banking apps or data are involved in this lab.

## Attacker (Alex Morgan)

```bash 
http://banking.test:5000/mail/attacker
alex.morgan@example.test
BlueCyan!4821
```

## Victim (Jordan Reed)

```bash 
http://banking.test:5000/mail/victim
jordan.reed@example.test
Password: intentionally unknown
```
