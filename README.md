# Introduction

This was the first technically-driven project that was done as part of the course requirement for IBM's i.am-vitalize programme. Its theme centered around the use of cloud computing capabilities to deploy and manage a solution. During our project team's idea brainstorming session, we had tapped into personal experiences of not getting good quality of sleep, which formed the main inspiration behind the project scope.

Our approach involved picturing ourselves as ambitious enterpreneurs that had set up a fictitious company called iSleep. We adopted the Enterprise Design Thinking framework to help us navigate through and stay aligned with the issue that we were motivated to address. At the same time, we acknowledged that some assumptions had to be made in the business context.

Within a tight project timeline of seven working days, we successfully prepared and presented the slides deck which is found in this repository. I had taken on the challenge of speaking about the logical dataflows, cloud and system architecture, DevOps SDLC (Software Development Lifecycle), and CI/CD (Continuous Integration / Continuous Deployment) pipeline. My primary objective was to convey technically-heavy jargons and concepts in a simple and concise manner.

The following was covered during the team presentation of the cloud architecture:

*We have decided to go to the cloud for iSleep’s system architecture in order for us to reap the benefits arising from cloud adoption, and IBM Cloud is our choice of cloud provider. Our cloud model adopts the Virtual Private Cloud (VPC) as our deployment model with Platform as a Service (PaaS) as our service model. We are going with VPC as we are able to leverage on the lower cost of ownership of a private cloud while having the infrastructure and security tailored to iSleep’s unique needs, and PaaS because it allows us to focus on managing the application and users’ data. We have chosen Tokyo to be the availability zone in IBM Cloud as we prefer to stay as close as possible to our initial target audience who are mostly located in Singapore.*

*Our cloud system architecture has been designed in the following manner. Starting from the user launching the iSleep application on his/her mobile phone, it brings the user to the app UI which is TLS encrypted, then to the API gateway. As the user will be required to log in with his/her email address and password, the data would flow from the authentication service, to the "Customer Identity” microservice, to IBM Cloud’s Identity and Access Management which would authenticate and authorise user access based on the client information stored in the secured database. Once this process is completed, the service discovery, which functions as a roadmap to aid communication between APIs, directs the data flow as per how iSleep users navigate the application. This is further enabled through the use of Eureka, a tool that deploys, monitors and manages the microservices.*

*Excluding the “Customer Identity” microservice, we also have seven other microservices in place, namely “Notification Alert”, “Alarm”, “Music”, “Analysis”, “Statistics”, “Wearable” and “Payment”. The microservices are overseen by IBM Cloud’s Kubernetes Service, which securely manages our overall container workloads by providing intelligent scheduling, self-healing, horizontal scaling for quick deploying, updating and scaling of microservices when needed. Having Istio as an add-on provides the additional ability to connect, control, observe and secure the microservices seamlessly. We will now look at the various IBM Cloud services that run with each microservice.*

*Both “Notification Alert” and “Alarm” microservices are linked to IBM Cloud’s Push Notifications, as we use these microservices to trigger notification alerts to iSleep users.*

*Since we need to link the “Music” microservice to Spotify outside iSleep’s cloud environment, we have an internet gateway in place with TLS encryption to facilitate this function.*

*The “Analysis” microservice is designed to generate sleep graphs and analysis after each iSleep user’s sleep experience whereas the “Statistics” microservice is intended to produce statistical comparisons with other iSleep users of similar lifestyle habits. Users are able to view these information from their dashboard by navigating to the “Journal” and “Statistics” pages respectively. Both microservices are empowered through the use of IBM Watson Machine Learning.*

*In order for us to better understand what iSleep users really experience before, during and after their sleep journey, data collected through their wearable devices, which is in the form of a ring for MVP1, would pass through the “Wearable” microservice for a more comprehensive sleep analysis. This microservice is enabled with IBM Watson IoT Platform. To establish closer collaboration work with NUS’ medical researchers, we also have a secured internet gateway that connects to their server.*

*As for the “Payment” microservice, it is linked from eNETS to the respective payment providers through a payment gateway that is secured.*

*Besides enabling security features in IBM Cloud, we have decided to put up additional firewalls surrounding our cloud environment as an extra fence of protection against possible malicious threats.*

*We have chosen to use IBM Cloudant for our database as we would be able to tap onto its ability to manage both structured and unstructured data. While we expect to collect structured data during the MVP1 phase, as our wearable device would eventually be capable of collecting other types of data that could come in the unstructured data format, we are confident that IBM Cloudant would be able to meet this data storage requirement. Since our target users for MVP1 are predominantly based in Singapore and data will be collected from Singapore, we have selected the nearest IBM Cloud availability zone to be Tokyo. However, as we progressively expand to MVP2, in line with our plans to globalise iSleep, we will eventually select other regions during that phase. Additionally, we enable the built-in security features that IBM Cloudant provides, such as HTTPS API used for authentication, in-flight encryption and TLS, in order to maintain encryption of data in all areas.*

*IBM Cloud Object Storage would allow us to take a snapshot of our database for archiving purposes as the size of our database grows overtime. This would serve as a backup for any instances of disaster recovery that our business might experience.*

Thank you for your time.