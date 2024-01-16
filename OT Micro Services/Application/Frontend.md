
# Frontend Setup 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 12 Jan 2024   |     v1     | Aakash Tripathi | 15 Jan 2024    |

## Introduction
Frontend Web is a REACTJS based application that is the primary user-interface for OT-Microservices stack.The app is designed for cross-platform fuctionality and requires only the presence of javascript runtime modules.The ReactJS based web framework facilitates complete web page based operations.

## Key Components
**REACTJS Framework**: The frontend uses REACTJS which is a declarative, efficient, and flexible JavaScript library for building user interfaces, particularly single-page applications where components update efficiently in response to data changes.
***
## Pre-requisites

## System Requirements
| Hardware Specifications | Minimum Recommendation |
| ----------------------- | ---------------------- |
| Processor | 1 CPU, t2.micro EC2 | 
| Ram | 1 GiB |
| Disk | 8 GB |
| OS | Ubuntu 22.04 LTS |
***
## Dependencies
### Build time Dependency
| Name | Version | Description |
| ---- | ------- | ----------- |
| GNU make | 4.3 | To build form Makefile |
| Npm | 8.5.1 | Package manager for Javasrcipt |

### Run time Dependency
| Name | Version | Description |
| ---- | ------- | ----------- |
| Nodejs | v12.22.9 | Javasrcipt runtime environment |

# Important Ports
| OutboundTraffic	 | Description |
| ---------------- | ----------- |
| 3000 | Default REACTJS port |

***
## Architecture

***
## Step-by-step installation of [application]
### Step1: Installation of software Dependencies
#### Install Dependencies:
* Install GNU make
    ```shell
       sudo apt update 
       sudo apt install make
    ```
* Install NPM
    ```shell
       sudo apt install npm
    ```
### Step2: Build Generation
* Create index.html file    
  Create a directory name public and create index.html file inside it with the following content:  
    ```shell
       <!DOCTYPE html>
       <html lang="en">
        <head>
          <meta charset="utf-8" />
          <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
          <meta name="viewport" content="width=device-width, initial-scale=1" />
          <meta name="theme-color" content="#000000" />
          <meta
           name="description"
           content="Web site created using create-react-app"
            />
          <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
          <!--
          manifest.json provides metadata used when your web app is installed on a
          user's mobile device or desktop. See https://developers.google.com/web/fundamentals/web-app-    manifest/
          -->
          <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
          <!--
          Notice the use of %PUBLIC_URL% in the tags above.
          It will be replaced with the URL of the `public` folder during the build.
          Only files inside the `public` folder can be referenced from the HTML.
          Unlike "/favicon.ico" or "favicon.ico", "%PUBLIC_URL%/favicon.ico" will
          work correctly both with client-side routing and a non-root public URL.
          Learn how to configure a non-root public URL by running `npm run build`.
          -->
          <title>React App</title>
        </head>
        <body>
          <noscript>You need to enable JavaScript to run this app.</noscript>
          <div id="root"></div>
          <!--
          This HTML file is a template.
          If you open it directly in the browser, you will see an empty page.
          You can add webfonts, meta tags, or analytics to this file.
          The build step will place the bundled scripts into the <body> tag.
          To begin the development, run `npm start` or `yarn start`.
          To create a production bundle, use `npm run build` or `yarn build`.
          -->
        </body>
     </html>
    ```
*  Set the maximum heap size (memory limit)
    ```shell
       export NODE_OPTIONS="--max-old-space-size=8192"
    ```
* Build the Application 
    ```shell
       make build
    ```
### Step3: Application Deployment
* Run the following command
    ```shell
       npm start
    ```
Once the above command is run, the frontend becomes accessible via browser at http://<host-ip>:3000
***


# Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co

# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
