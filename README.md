# S3URL
> S3URL application shortens, saves and share your URLs with the world. Generated URLs can seamlessly be shared on social media platforms like Twitter and tracked/managed in the “My account” page. The simplicity of S3URL is powered under the hood by cutting edge technology.  S3URL completely runs in a self-managing environment with the help of Kubernetes. The entire fleet of micro services are run as Docker containers inside of Kubernetes. At S3URL we are big believers of CI/CD and we use Jenkins-X for just that. Whenever code is checked into our source repositories, it is automatically pulled by Jenkins, tested and deployed to staging servers.The entire system is monitored using Prometheus and centralized dashboards show the behavior of all the micro services. PagerDuty integration makes sure that we are alerted immediately when an issue occurs so that we can jump on it. Centralized logging through BEK (Beats, Elasticsearch, Kibana) helps our developers to rapidly debug issues that are reported by customers. Our NoSQL databases are built to scale for any number of customers that come on board. The entire experience for customers and developers is backed by our intuitive SSO that can expose different role based views.

[![S3URL-Home](https://i.imgur.com/qdwHso4.png)](https://i.imgur.com/qdwHso4.png)

------

## Product Perspective
> The product is designed with a parent product like bitly. In addition to the shorten URL service, we have implemented Single Sign On with three essential applications Jenkins, Kibana and Grafana. Both these tools are used to store the source code and  build test pipeline continuously. All our services are containerized and managed using Kubernetes. We have used Jenkins-X to implement continuous integration and continuous deployment. This includes centralized monitoring using Elastic search and Prometheus. Visualize all logs and metrics using Grafana and Kibana. We have also integrated this application with other social applications like twitter and PayPal.

## Product Functions
> A user can create a new account by normal sign up or Google sign in to our application. Users are allowed to generate shorter URL for  any long URL that they desire. We have maintained confidentiality by providing them a profile space where the users can see their history, list of their shorter URL with the long URL and the date on which they generated it. We also provide user to share the shorter URL in the tweeter social website. Developers also need to have access to monitor this application. We have implemented Single Sign On with Cognito This allows developers to login to gigs and Jenkins directly from this application. Moreover, we have monitored the logs and metric using   applications like Elasticsearch, Kibana, Prometheus, Jenkins, Grafana for CI/CD feature. 

## User Classes and Characteristics
> We have classified two user classes who can use our application. The users who need to generate a short or a customized URL for their blogs, articles, social website links. These users can create a new account with their email and password. Login at anytime and generate their required short URL. They are also provided a profile page where they can get and manage the list of all their URLs. Another user class is developers. The users are allowed to share their shorten Urls in their social websites. Developers who have designed this website or developers who are curious to know about the source code or the build dates of test files can login using their developer email account. They are provided with single sign on feature by which they can sing in Kibana, Grafana and the jenkins in the developer’s dashboard.


## Operating Environment
The S3URL website is build as a three tier MVC application where the front-end is implemented using HTML, Javascript (jQuery), and Ajax, backend using golang with amazon Dynamodb database. This application is containerized as docker images and deployed using Jenkins-X using kubernetes platform. In Jenkins-X we have leverage the continuous integration and testing with Jenkins, complete monitoring of the application using Prometheus. We have also implemented visualization feature called Grafana to provide easily  understandable graphs to monitor and predict the behavior of the application with the metrics data in Prometheus. We have utilized Elasticsearch search engine with Beats and Kibana which is a data visualization plugin for Elasticsearch.


## Design and Implementation Constraints
When we decided to utilize various platforms like Kibana, Jenkins, Grafana, Prometheus, Elasticsearch, Beats etc. The major issue that we faced was configuring multiple platforms with multiple signup accounts. Connecting each of these platforms with our application was another huge drawback. We searched for a suitable tool tag combines all these features and just allows to deploy our application once. We finally came to know about Jenkins-X which satisfies this requirement.

-----

## User Interfaces
>S3URL allows both user and developers to Signup a new account and login at anytime. It also provides an essential facility for users to maintain their related data in their profile. The My account page allows the user to keep track of all their long URLs with their generated shorten URLs and date on which they generated it. In addition to this user interface facility, we have also implemented a place where the users can share their URLs to their twitter account. They can edit their post if required. On the other hand, the graphic user interface is completely build using HTML, CSS,JS and made responsive to adjust the layout for different machine sizes. The developers also maintain an account  where they are provided to Single Sign On in to both Grafana, Jenkins and Kibana in order to reduce their valuable time in creating accounts, signing in with different usernames and so on. Moreover, the developers are authorized to maintain the source code and keep an update on the testing pipeline in Jenkins. The main feature is Shorten URL. The user interface provides the users a simple text box with a one click button that generates the required shorten URL and records the time and details to the user profile. It is simple and secure. Overtime the user clicks the shorten URL, the URL automatically redirects to the original link. This reduces the pressure in the minds of the users to remember a long hashed URL and  helps them to save their URLs for future reference.

### STEP 1: SSO login/signin
[![S3URL](https://i.imgur.com/qKUAVg1.png)](https://i.imgur.com/qKUAVg1.png)

### STEP 2: Generate a short URL for a long URL 
[![S3URL](https://i.imgur.com/qdwHso4.png)](https://i.imgur.com/qdwHso4.png)

### STEP 3: Check the history in the user account
[![S3URL](https://i.imgur.com/FmWkqgL.png)](https://i.imgur.com/FmWkqgL.png)

### STEP 4: Donate money to an NGO organization using Paypal Donate
[![S3URL](https://i.imgur.com/PocVD5k.png)](https://i.imgur.com/PocVD5k.png)

### STEP 5: Share the shortened URL in social websites
[![S3URL](https://i.imgur.com/qbVGx2H.png)](https://i.imgur.com/qbVGx2H.png)


## Hardware Interfaces
> This application is a simple web application which needs a web browser to run. We have used golang to implement the URL shorten APIs and Single Sign On for developers. We have to run the application in the go server. The softwares we have used can be configured in the localhost or with a public domain. This other tools like Prometheus, PagerDuty, Elasticsearch, Beats, Kibana, Grafana are completely based on one time configuration in their portals and continuous integration and delivery of the jenkins pipeline.

### Architecture Diagram:
[![Architecture Diagram](https://i.imgur.com/lwH6Rqp.png)](https://i.imgur.com/lwH6Rqp.png)

### CI/CD Pipeline: 
[![CI/CD Workflow](https://i.imgur.com/V2Xvqfw.png)](https://i.imgur.com/V2Xvqfw.png)

### Cognito SSO: 
[![Cognito SSO](https://i.imgur.com/cmMG1WW.png)](https://i.imgur.com/cmMG1WW.png)


## Software Interfaces
> S3URL web application is build using golang and run on the go server. We have implemented the Single Sign On feature which is configured using Cognito that runs above the TCP/IP stack layer in order to connect to or modify the directories in the internet. . We have used NoSQL databases to scale for any number of customers that come on board. Cognito server directs the user login credentials to the  Kibana, Grafana and Jenkins server to allow single sign on ability. The entire web application is deployed as docker containers with kubernetes using Jenkins-X. Jenkins-X provides an end to end development platform in which our S3URL can be built, tested and deployed with CI/CD.

[![CI/CD](https://i.imgur.com/hVhwJuw.png)](https://i.imgur.com/hVhwJuw.png)


[![Grafana1](https://i.imgur.com/qcCkCGi.png)](https://i.imgur.com/qcCkCGi.png)


[![Grafana2](https://i.imgur.com/2puoSUr.png)](https://i.imgur.com/2puoSUr.png)


[![Kibana](https://i.imgur.com/co7IGHV.png)](https://i.imgur.com/co7IGHV.png)

## Communications Interfaces
> The application entirely communicates using REST APIs for shorten URL service, Cognito for user login credentials which are saved in DynamoDB. Our application is build as microservices to leverage the loosely coupled capabilities and allows continuous integration and delivery.. We have used Cognito  server to accelerate the performance by compressed inbound and outbound traffic data and also provides header for backend servers which acts as a defense against security threats/attacks. Cognito’s OpenID Connect provides the single sign on feature with jenkins, Grafana and the application itself. Jenkins-X acts as a single platform that puts the code through continuous integration and provides seamless deployment. We used GKE deploy the entire kubernetes infrastructure and installed Jenkins-X on top of it. We can view the entire building and testing pipeline in the dashboard provided by Jenkins.

### Sequence Diagram: 
[![Sequence Diagram](https://i.imgur.com/IHCMyLs.png)](https://i.imgur.com/IHCMyLs.png)


[![Sequence Diagram2](https://i.imgur.com/EB9ndOa.png)](https://i.imgur.com/EB9ndOa.png)

## Project Accomplishments

>S3URL comes with a clean and simple interface to create, manage and share URLs. It is done both through a user interface and REST APIs. Angular.js helps us to deliver an experience that is clean, seamless and. Generated URLs can seamlessly be shared on social media platforms like Twitter and tracked/managed in the “User dashboard” page. The simplicity of S3URL is powered under the hood by cutting edge technology.  S3URL completely runs in a self-managing environment with the help of Kubernetes. The entire fleet of micro services are run as Docker containers inside of Kubernetes. At S3URL we are big believers of CI/CD and we use Fabric8 for just that. Whenever code is checked into our source repositories, it is automatically pulled by Jenkins, tested and deployed to staging servers. The entire system is monitored using Prometheus and centralized dashboards show the behavior of all the micro services. PagerDuty integration makes sure that we are alerted immediately when an issue occurs so that we can jump on it. Centralized logging through BEK (Beats, Elastic search, Kibana) helps our developers to rapidly debug issues that are reported by customers. Our NoSQL databases are built to scale for any number of customers that come on board. The entire experience for customers and developers is backed by our intuitive SSO that can expose different role based views. S3URL is built for scalability, reliability and high availability. If you believe in our vision, then go ahead and tap on the “Donate now” to donate via PayPal. List of features we have accomplished with application. 

[![Jenkins](https://i.imgur.com/Ebt2UYW.png)](https://i.imgur.com/Ebt2UYW.png)

[![Jenkins](https://i.imgur.com/jvV5FLV.png)](https://i.imgur.com/jvV5FLV.png)

[![S3URL2](https://i.imgur.com/QWQDtXa.png)](https://i.imgur.com/QWQDtXa.png)

[![S3URL](https://i.imgur.com/Q1s4jJO.png)](https://i.imgur.com/Q1s4jJO.png)

- SSO based on Cognito and Google Sign on 
- Micro-service that shortens long URL.
- Micro-service that redirects web traffic.
- CI/CD is achieved via Jenkins-X.
- Twitter and PayPal integration


## Reference
- https://jenkins-x.io/   
- https://aws.amazon.com/cognito/ 
- https://www.linuxbabe.com/ubuntu/install-configure-openldap-server-ubuntu-16-04
- http://www.zytrax.com/books/ldap/ch11/groups.html

## Appendix

### Appendix A: Glossary
S3URL(shortens, saves and share your URL), Jenkins-X, Docker, Kubernetes, Prometheus, Elasticsearch, Beats, Kibana, Grafana, PagerDuty, Cognito, SSO (Single-Sign-On), Jenkins, Github.
