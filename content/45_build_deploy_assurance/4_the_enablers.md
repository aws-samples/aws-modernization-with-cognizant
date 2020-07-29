+++
title = "The Enablers "
chapter = false
weight = 4
+++



In addition to the practices we discussed so far, Service Virtualization (SV) and Test Data Management (TDM) are two enablers that are most critical to the successful implementation of QA in DevOps, since they both result in laying a strong foundation for testing in general and automation in specific. As this workshop focuses on the execution stage, let us discuss their basic concepts and high-level approach. 

#### Service Virtualization

Unavailability of environment needed for testing, is the one of the key bottleneck for Continuous Testing in DevOps.  This unavailability could be because of many reasons like under development services, shared environments, constraint on access, performance issues (or) due to high cost of usage for third-party interfaces. 

Traditionally development teams solved some of the challenges with stubbing that needs high programming skills and lacks flexibility. Service Virtualization is a modern way to resolve above environment challenges and offers higher flexibility and ease for implementation.  

Service Virtualization (SV) is a practice of ‘Capturing and Simulating’ the responses, data and performance of real systems and deploying a Virtual Service to replace them. SV focuses on mimicking the particular interfacing service rather than mimicking an entire application.

![](/images/module2/4-1.png)

There are multiple tools available for implementing Service Virtualization, with support for communication (HTTP, MQ, TCP, etc.) and data (SOAP, JSON, SWIFT, etc.) protocols. To make it easy to implement, these tools provide multiple options to create virtual services (from WSDL, with Request/Response [R/R] pair, using recording etc.) to maintain the same (like auto heal, live compare etc.). Once created, Virtual services can be deployed using continuous testing pipeline on demand. 
This not only reduces environment dependency and associated idle time for testing teams but also increases test coverage with early defect detection.  SV brings in much needed agility in testing lifecycle and cuts down the overall release timelines. Its rapidly growing industry adoption is a testimony to the fact that Service Virtualization is acknowledged as a key enabler for QA in DevOps.


#### Test Data Provisioning

After test environment, Test data has been traditionally the pain area for Quality Assurance. A brilliantly thought-out QA process is bound to fail if the test data it employs is not available (or) is not as per the test specification. Further, the process of provisioning data into the test environments and the data refresh cycles is usually a time consuming, laborious and complex task. If not managed well, test data can be the quintessential bottleneck that can derail continuous testing pipelines.

QA teams needs accurate and secure data for test execution and need it fast as well. There are essentially two alternatives approaches possible for test data provisioning in test environment viz. sub-setting the production data or creating synthetic data. 

While sourcing data from production environments, it is crucial to mask PPI / Sensitive information to avoid data privacy risk and regulation issues. While creating entire data synthetically, can also be a very complex and a laborious process in real time. Thus, the best practice is to have a right blend of both the techniques to achieve agility and security in the data provisioning process.
    
Along with the traditional practices, on-demand data provisioning with self-help portals and data virtualization are modern trends that are growing in industry adoption. DevOps ready enterprise wide test data management solutions are fast gaining their long due respect as the key enablers for efficient and agile testing life cycle.




