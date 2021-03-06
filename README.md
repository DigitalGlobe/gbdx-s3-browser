# gbdx-s3-browser
Simple web GUI for browsing/downloading S3 attached to a GBDX account.  Relies on the AWS javascript SDK (http://docs.aws.amazon.com/AWSJavaScriptSDK/guide/browser-examples.html)

![Screenshot](example.png?raw=true "Screenshot")

Run from Dockerhub:
--------
```bash
sudo docker run -e GBDX_API_KEY=YOUR_GBDX_API_KEY -p 80:8080 nricklin/gbdx-s3-browser
```

Build and Run Docker container:
-------
```bash
# Clone the repo and cd inside:
git clone https://github.com/nricklin/gbdx-s3-browser
cd gbdx-s3-browser

# build the Docker image
sudo docker build -t gbdx-s3-browser .

# Run the docker image:
sudo docker run -e GBDX_API_KEY=YOUR_GBDX_API_KEY -p 80:8080 gbdx-s3-browser
```

Run Locally (without Docker):
--------
```bash
# Clone the repo and cd inside:
git clone https://github.com/nricklin/gbdx-s3-browser
cd gbdx-s3-browser

# Create a virtualenv and install python requirements
virtualenv venv
. venv/bin/activate
pip install -r requirements.txt

# set required env vars
export GBDX_API_KEY=<YOUR_GBDX_API_KEY>
export TOKEN_URL=https://geobigdata.io/auth/v1/oauth/token/
export S3CREDS_URL=https://geobigdata.io/s3creds/v1/prefix

# run the application
python application.py
```

Deployment:
----

To deploy to AWS Elastic Beanstalk:

Create a zipfile containing:

* application.py
* the lister directory & its contents
* the Dockerfile
* requirements.txt

Then upload to beanstalk.

TODO:
----
- Make it work in Safari
- ~~Display user information up top~~
- ~~Enable upload~~
- ~~Enable folder creation~~
- ~~Make the sort order work properly~~
- Verify everything works when there are more than 1000 keys in a folder
- ~~Pull all javascript and css local~~
- bad password (or other error) returns 500.   It should popup at you.
- ~~Enable Delete~~
- ~~Enable HTTPS~~ (can put behind an https proxy)

