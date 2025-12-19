## Installation links

## install youtube
https://www.youtube.com/watch?v=gjWaOrqK5uY

# Overview of docker installation
https://opensource.hcltechsw.com/domino-container/quickstart/

## Supported environments
https://opensource.hcltechsw.com/domino-container/concept_environments/

## Download portal for customers
https://my.hcltechsw.com/

## Install docker container process

Below are clear, concise bullet points to install the HCL Domino Docker Trial in an enterprise-friendly, step-by-step manner.

Prerequisites

Docker Engine installed

Docker Desktop (Windows/macOS) or Docker Engine (Linux)

Minimum system requirements:

8 GB RAM (16 GB recommended)

4 CPU cores

30+ GB free disk space

Valid HCL Domino Trial license

HCL ID (required to download images)

Internet access for image pull

Step 1: Create HCL ID and Accept License

Create or log in with your HCL ID

Accept the HCL Domino Container License Agreement

Download the Domino trial license file (.lic)

Step 2: Log in to HCL Container Registry

Open terminal or command prompt

Authenticate Docker with HCL registry:

docker login hclcr.io


Use your HCL ID and password

Step 3: Pull Domino Docker Image

Pull the official Domino image:

docker pull hclcr.io/domino/domino:latest


Verify image download:

docker images

Step 4: Prepare Local Directories

Create folders for persistent Domino data:

/local/domino/data

/local/domino/license

Copy the trial .lic file into the license folder

Step 5: Run Domino Setup Container

Start Domino in interactive setup mode:

docker run -it \
  -p 1352:1352 \
  -p 80:80 \
  -p 443:443 \
  -v /local/domino/data:/local/notesdata \
  -v /local/domino/license:/licenses \
  hclcr.io/domino/domino


Domino setup wizard starts automatically

Step 6: Complete Domino Server Configuration

Choose “First Server”

Provide:

Organization name

Server name

Admin user credentials

Point license path to /licenses

Complete server initialization

Step 7: Access Domino Administrator

Open browser:

https://localhost

Log in using Domino Admin credentials

Verify:

Server status

Names.nsf created

HTTP task running

Step 8: Persist and Restart Container

Stop container after setup

Restart Domino in detached mode:

docker run -d \
  --name domino \
  -p 1352:1352 \
  -p 80:80 \
  -p 443:443 \
  -v /local/domino/data:/local/notesdata \
  hclcr.io/domino/domino

Step 9: Validate Installation

Access:

Domino Administrator (Notes client or browser)

Web access via browser

Check logs:

docker logs domino

Optional (Recommended for Enterprise Trial)

Enable HTTPS certificates

Configure mail routing

Enable Nomad Web or Traveler

Backup /local/notesdata directory

Use docker-compose for repeatable setup