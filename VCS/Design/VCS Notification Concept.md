
# VCS Notifications Concept 

|   Authors        |  Created on   |  Version   | Last updated by | Last edited on |
| -----------------| --------------| -----------|---------------- | -------------- |
| Aakash Tripathi | 18 Jan 2024   |     v1     | Aakash Tripathi | 19 Jan 2024    |
***
## Table Of Contents 
1. Introduction
2. Why Notifications
3. Types of Notifications
4. Events for VCS Notifications
5. Conclusion
6. Contact Information
7. Refrences
***
## Introduction
Frontend Web is a REACTJS based application that is the primary user-interface for OT-Microservices stack.The app is designed for cross-platform fuctionality and requires only the presence of javascript runtime modules.The ReactJS based web framework facilitates complete web page based operations.
***
## Why VCS Notifications
Why we need vcs notifications 
***
## Types of Notifications 
The frontend application have dependencies on other REST API of **[OT-Microservices](https://github.com/OT-MICROSERVICES)**. To run the application successfully, we need these things configured:

## Events for VCS Notifications 

## Conclusion
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
