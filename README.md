# Find-my-iphone
Link icloud, spreadsheet, and mapbox, and record iphone's location information &amp; history in spreadsheet.  

<img src="https://img.shields.io/badge/Chrome-Passing-gre.svg?logo=Google%20Chrome&amp;style=plastic">

![sample](img/sample.png "sample.png")

## PREPARE
```
git clone git@github.com:makobouzu/Find-my-iphone.git
cd find-my-iphone
npm install
```

```
touch .env
```
### .env file include
+ PORT
+ APPLE_ID
+ PASSWORD
+ SPREADSHEET_ID
  + `https://docs.google.com/spreadsheets/d/XXXXXXXXXXXXXXXXXXXXXXXXXXX/edit#gid=0` -> SPREADSHEET_ID="XXXXXXXXXXXXXXXXXXXXXXXXXXX"
+ SHIFT_WORKSHEET_ID 
  + `https://docs.google.com/spreadsheets/d/XXXXXXXXXXXXXXXXXXXXXXXXXXX/edit#gid=0` -> SHIFT_WORKSHEET_ID="0"

### Enable Google Spreadsheet API  
Go to [Google Cloud Platform] (https://console.cloud.google.com/home)-> Create new Project-> Go to "APIs and Services"-> Click "Enable APIs and Services"-> Enable Google Sheets API

Click "Create Credentials"-> API to use = Google Sheets API & Data type to access = Application data (No, not used)-> Write service account (Role = Editor)-> "Done" 

Click "XXXX-XXX@XXXXXXXXX.gserviceaccount.com" in Service Account-> Click "Add Key (Create New Key)" in Key-> Download json-> rename credentials.json & mv ./routes

Share E-mail(client_email: XXX@XXXXXX.gserviceaccount.com in credentials.json) in Spreadsheet settings -> Editor

* Reference
   * [How to read shift data from Google Spreadsheet with Node.js] (https://www.twilio.com/blog/load-data-from-google-spreadsheet-jp)

### Create Mapbox Access Token  
Sign in [mapbox](https://account.mapbox.com/auth/signin/) -> Copy default public token -> Paste mapboxgl.accessToken in index.js:4

* Reference
  * [mapbox reference](https://docs.mapbox.com/help/getting-started/access-tokens/)  

## RUN
```
cd find-my-iphone
npm run devStart
```

## REFERENCE
* [find-my-iphone](https://www.npmjs.com/package/find-my-iphone)
* [google-spreadsheet](https://www.npmjs.com/package/google-spreadsheet)
