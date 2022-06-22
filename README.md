# Snyk Automatic Ticketing

If you want automic ticketing for new issues - we got your back!

This project let's you publish yesterday's vulns to ANY ticketing board that you use. Assuming they have a Rest API.

## Setup

### 1. Fork this Project

You'll need to fork and edit this repo for yourself to make the last "publish ticket" API call work.


### 2. Get your Snyk Token & Org ID 

Your Snyk Token authenticates every Snyk API call.

Your Org ID specifies which Org to filter issues for.

Get these two values, then set `SNYK_TOKEN` and `SNYK_ORG` as Python env-vars, respectively.

### 3. Setup a virtual environment

*Be sure to replace `XXX` and `YYY` with your Snyk Token and Org ID.*

```
# Inside snyk-python-yesterday-vulns
python3 -m venv venv

# Add env vars
echo "export SNYK_TOKEN=XXX" >> venv/bin/activate
echo "export SNYK_ORG=YYY" >> venv/bin/activate

# Install dependencies
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt

# Run the script
python publish_new_vulns.py
```

### TODO: Complete your publish API call

This boilerplate project just runs `pprint` on yesterday's issues. If you want them on your board, figure out your board's Rest API and add the final `requests.post(...)` call.

Then you should be good to go!