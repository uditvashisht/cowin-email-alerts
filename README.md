# CoWin Email Alerts

This is a script which can be used to send email alerts to your desired email in case COVID's vaccination slot is available on COWIN.

## Prerequisites

* A gmail account and password.
* An app password if you have 2-Step Verification enabled on your gmail account. Follow this [link](https://saralgyaan.com/posts/use-python-to-send-email/) to learn to setup your account.

Note: You can also use other email accounts but for that you will have to change email server and PORT at line 66 of the code (cowin-email-alerts.py)

## Requirements

* Python 3.9 or above (As the code uses [f-strings](https://saralgyaan.com/posts/f-string-in-python-usage-guide/))
* cowin (pip install cowin)
* pandas

You can use the following command to install all the requisite modules:-
`pip install -r requirements.txt`

## Installation

Either download the directory from github or clone it using:-

`https://github.com/uditvashisht/cowin-gmail-alerts.git`

```
cd cowin-gmail-alerts
python3 -m venv . #You can use python or python3 or python3.6 depending on your system
source bin/activate
pip install -r requirements.txt
```

## Usage

Adding your email credentials

You can add the FROM_EMAIL, TO_EMAIL, PASSWORD (for FROM_EMAIL) either at line 11-13 of the python code (cowin-email-alerts.py) or
your can use python-decouple or [environment variables](https://saralgyaan.com/posts/set-passwords-and-secret-keys-in-environment-variables-maclinuxwindows-python-quicktip/)

Create a .env file and add your credentials

```
FROM_EMAIL=
TO_EMAIL=
PASSWORD=
```

Then you need to provide the following:-

1. No. of Days :- It should be added in line 16 of the code. Preferably 7,14,21 or 28 days should be added if add between 14 to 20 days it will give data for 14 days.

2. Pincodes :- You can add any number of pincodes in line 17. But the pincodes should be added as string separted by commas in a list. e.g ['141001', '152002', '152001']

3. Age :- To be added in line 18 of the code. Acceptable values are 18 or 45.

Then the script can be run as

``` python cowin-email-alerts.py```

Your will get an email like this

![Image of Gmail](https://github.com/uditvashisht/cowin-gmail-alerts/blob/master/img.png?raw=true)

You can either schedule to run the script at regular intervals or run it in the background after commenting out line 132 and uncommenting lines 136-138 of the code. It will run the script and check for the availability after every 15 minutes till you keep it running.

**Note:- You might change the name in the message at line 63 and the subject at line 57**
## To Do

Add option to get notification by Whatsapp.

## License
© 2021 Udit Vashisht This repository is licensed under the MIT license. See LICENSE for details.
