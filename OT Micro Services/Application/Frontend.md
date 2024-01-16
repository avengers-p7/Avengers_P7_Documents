
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
The frontend application have dependencies on other REST API of **[OT-Microservices](https://github.com/OT-MICROSERVICES)**. To run the application successfully, we need these things configured:

* **[Employee API](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Employee_API.md)**
* **[Attendance API](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Attendance_API.md)**
* **[Salary API](https://github.com/avengers-p7/Documentation/blob/main/OT%20Micro%20Services/Application/Salary_API.md)**

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
| npm | 8.5.1 | Package manager for Javasrcipt |

### Run time Dependency
| Name | Version | Description |
| ---- | ------- | ----------- |
| Nodejs | v12.22.9 | Javasrcipt runtime environment |

# Important Ports
| Inbound Traffic	 | Description |
| ---------------- | ----------- |
| 22 | For SSH |
| 3000 | Default REACTJS port |

***
## Architecture
<img width="600" length="400" alt="Frontend" src="https://github.com/avengers-p7/Documentation/assets/156056413/dcd818bb-7574-406c-9199-69cd2048d074">

***
## Step-by-step installation of [application]
### Step1: Installation of software Dependencies
#### Install Dependencies:
* Install GNU make
    ```shell
    sudo apt update 
    sudo apt install make
    ```
    ![Screenshot from 2024-01-16 14-50-37](https://github.com/avengers-p7/Documentation/assets/156056413/ca99a9e8-1ad7-4a50-864b-3f5e36dd322d)

* Install NPM
    ```shell
    sudo apt install npm
    ```
    ![Screenshot from 2024-01-16 14-52-07](https://github.com/avengers-p7/Documentation/assets/156056413/dad28260-d3bc-42c5-9fdd-630512fdb8d9)


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
    export NODE_OPTIONS="--max-old-space-size=512"
    ```
* Build the Application 
    ```shell
    make build
    ```
    ![Screenshot from 2024-01-16 14-53-09](https://github.com/avengers-p7/Documentation/assets/156056413/00874384-f41e-4c02-bd06-94eb66a1e68b)
    Once the build is successfull it is ready to be deployed.
    ![Screenshot from 2024-01-16 14-58-43](https://github.com/avengers-p7/Documentation/assets/156056413/dd8c438c-f596-412a-a788-830c893a5eeb)

### Step3: Application Deployment
* Run the following command
    ```shell
    npm start
    ```
    ![Screenshot from 2024-01-16 15-01-59](https://github.com/avengers-p7/Documentation/assets/156056413/a3111a70-3407-4751-bde2-fd4fdc8444f4)

    Once the above command is run, the frontend becomes accessible via browser at http://(host-ip):3000
    <img width="700" length="400" alt="Final Output" src="https://github.com/avengers-p7/Documentation/assets/156056413/f0c58cd1-7f39-445b-a90e-5edf2360b621">
***
## Troubleshoot
**Javascript heap out of memory error**
During the build phase one might encounter javascript heap out of memory error.
![Screenshot from 2024-01-16 00-25-27](https://github.com/avengers-p7/Documentation/assets/156056413/d5202499-699c-496e-a874-7b7662e26c7b)
This can be resolved using `export NODE_OPTIONS="--max-old-space-size=512"`    
**NOTE:** Ideally the size should not be more than half the size of memory(RAM) .

***
# Contact Information

| Name                 | Contact Information                                                                                     
|---------------------------------|------------------------------------------------------------|
| Aakash Tripathi                 |  aakash.tripathi.snaatak@mygurukulam.co
***
# References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| Frontend API | https://github.com/OT-MICROSERVICES/frontend |
| Javascript heap out of memory error |https://geekflare.com/fix-javascript-heap-out-of-memory-error/ | 
| Default index file for public folder | https://github.com/react-cosmos/create-react-app-example/blob/master/public/index.html |
