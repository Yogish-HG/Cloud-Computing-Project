# ShopVista - Your Shopping Gateway

## Project Overview

The E-Commerce Grocery and Food Delivery Web Application is a comprehensive online platform designed for users to conveniently purchase groceries and food products. The application prioritizes a personalized and secure experience by requiring user registration. Upon successful login, users are greeted with a user-friendly interface presenting a curated catalog of available items. Key features include secure authentication, an extensive product catalog categorizing items, and a streamlined order placement process for effortless selection of desired quantities. After confirmation, the system automatically generates invoices, and users receive email notifications containing payment details, ensuring a seamless and user-centric shopping experience.

## Key Objectives

### User-Centric Approach
- Prioritizing user satisfaction, the application employs a user-centric design to ensure a seamless and enjoyable shopping experience.
- User registration and authentication mechanisms are implemented to create a personalized and secure environment.

### Extensive Product Catalog
- The heart of the application lies in its comprehensive catalog, featuring a diverse range of groceries and food products.
- Items are meticulously categorized and accompanied by detailed descriptions and images to facilitate informed purchasing decisions.

### Effortless Order Placement
- Streamlining the order placement process, users can easily select the desired quantity of each item they wish to purchase.
- Intuitive design and navigation enhance the overall user experience, making it accessible for users of varying technological proficiency.

### Automated Invoice Generation
- Upon order confirmation, the system automatically generates detailed invoices summarizing the selected items and quantities.
- Users receive email notifications containing these invoices, along with payment details, ensuring transparency and accountability.

### Order History and Tracking
- The system maintains a comprehensive order history for users to reference their previous purchases.
- Real-time order tracking enhances transparency, allowing users to monitor the status of their deliveries.

## AWS Services used

### Compute

#### 1. Elastic Beanstalk

Elastic Beanstalk stands out as a superior deployment option when compared to Amazon EC2 or Docker in specific scenarios. Its primary strength lies in abstracting the intricacies of infrastructure management, offering a streamlined experience for developers. With Elastic Beanstalk, tasks like capacity provisioning, load balancing, and auto-scaling are automated, allowing developers to concentrate solely on their application code. The platform's ease of use is highlighted by a user-friendly interface and command-line tools, simplifying deployment and management tasks. Furthermore, Elastic Beanstalk excels in automatic scaling, ensuring optimal resource utilization based on application demand, a feature that requires more manual effort with EC2 and additional orchestration tools with Docker.

#### 2. AWS Lambda

AWS Lambda provides a versatile solution for building event-driven applications by enabling the seamless execution of code in response to various triggers, such as HTTP requests or modifications to data in Amazon S3. This flexibility allowed me to easily construct applications that respond dynamically to specific events. The integration capabilities of AWS Lambda extend beyond its core functionality, allowing for smooth collaboration with other AWS services like DynamoDB and SNS. The strength of AWS Lambda lies in its ability to simplify the execution of code in a scalable and cost-efficient manner.

### Storage

#### 1. AWS Dynamo DB

I've opted for Amazon DynamoDB as the storage solution for my project details within the AWS environment. This choice is attributed to the platform's user-friendly nature, eliminating the need for manual server setup or backup management, as AWS handles these aspects seamlessly. DynamoDB's automatic scalability aligns perfectly with the dynamic nature of my application, effortlessly adapting to varying data loads. Its notable speed ensures swift data access for users. The service's flexibility allows for easy modifications and additions to data fields as my application evolves over time. DynamoDB's seamless integration with other AWS services contributes to building a reliable and interconnected application. Additionally, the service prioritizes data security and availability, providing reassurance even in the face of potential issues. In essence, DynamoDB strikes the right balance between simplicity, scalability, speed, and reliability, making it an ideal choice for my application.

#### 2. AWS S3

I have employed Amazon S3 buckets to store essential components of my project, including the zipped file for my React app and Lambda functions. These stored artifacts serve a pivotal role in my configuration setup, where the deployment process for AWS Elastic Beanstalk and Lambda functions is orchestrated. Utilizing S3, I can seamlessly integrate the code for Lambda functions and deployment zip files into my configuration files, ensuring efficient retrieval and deployment processes for both AWS Elastic Beanstalk and Lambda services.

### Network

#### 1. API Gateway

An API gateway serves as a crucial component in modern software architecture by providing a unified entry point for clients to interact with various microservices. It simplifies client-server communication, consolidating multiple service endpoints into a single, easily accessible interface. This not only reduces the complexity of interactions for clients but also streamlines the development process. Security is a paramount concern in distributed systems, and API gateways play a pivotal role by centralizing security measures such as authentication, authorization, and encryption. This ensures a secure communication channel between clients and microservices, mitigating potential vulnerabilities. Load balancing is another key feature of API gateways, optimizing resource utilization by distributing incoming requests across multiple instances of microservices. This not only improves system reliability but also enhances scalability as the application can efficiently handle increased traffic. Additionally, API gateways offer robust monitoring and analytics capabilities, providing real-time insights into API usage, performance metrics, and error rates. This centralized monitoring facilitates proactive issue resolution, ensuring the overall health and performance of the system.

### General

#### 1. AWS SNS (Simple Notification Service)

I have used AWS SNS for sending email to the customers whenever they order items. I create a topic using their email id which is unique for each user when they register for the app. I store the ARN of these topics in the customer database. Whenever a user orders from the app, I just send the invoice of the items and also the payment details through which the user will make the payment.

#### 2. Infrastructure as code (Cloud Formation)

CloudFormation is a game-changer for me in AWS, serving as a fundamental tool for Infrastructure as Code (IaC). It empowers me to define and provision AWS resources in a declarative manner, using templates in JSON or YAML format. This approach brings consistency and repeatability to my infrastructure setup, mitigating the risk of configuration errors and making resource management more efficient. When it comes to Continuous Integration and Continuous Deployment (CI/CD), CloudFormation takes center stage in my workflow. By representing my infrastructure as code, I seamlessly integrate CloudFormation templates into my CI/CD pipelines. This integration ensures that changes to my infrastructure are treated with the same level of control and automation as changes to my code, fostering collaboration between my development and operations teams. Examining my CloudFormation script, I see how it orchestrates the creation of various AWS resources – DynamoDB tables, Lambda functions, an API Gateway, and an Elastic Beanstalk environment – all of which are essential for my web application. In the CI/CD context, every modification triggers a pipeline where the CloudFormation template is deployed automatically. This ensures that infrastructure changes align with code changes, creating a unified and efficient deployment process. CloudFormation's ability to version my infrastructure is a crucial aspect of my CI/CD practices. It allows me to track, test, and deploy changes incrementally. If issues arise, I can easily roll back to previous configurations, following the best practices of CI/CD.
