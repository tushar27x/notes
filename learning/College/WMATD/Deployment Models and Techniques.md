Define how the applications are distributed, installed and made accessible to the end-user.

### **Deployment Models**

- **On-Premise Deployment** -> The application is deployed on the organization’s servers, providing full control over the environment but requiring significant infrastructure and maintenance resources.

- **Cloud Deployment** -> The application is hosted on cloud platforms like AWS, Azure, or Google Cloud. It offers flexibility, scalability, and reduced infrastructure costs, and can be configured as:
	- **Public Cloud**: Resources are shared with other organizations but isolated.
	- **Private Cloud**: Dedicated resources on the cloud for a single organization, offering more control and security.
	- **Hybrid Cloud**: A combination of public and private clouds, providing both flexibility and security.

- **Containerized Deployment** -> Applications are packaged in containers (e.g., Docker) with all necessary dependencies, enabling consistency across environments and easier scaling.

- **Serverless Deployment** -> Application functions run as event-triggered services without managing underlying infrastructure, commonly using platforms like AWS Lambda or Google Cloud Functions.


### **Deployment Techniques**

- **Continuous Deployment (CD)** -> An automated process where code changes are deployed directly to production after passing tests. Requires extensive automation and monitoring to ensure stability.

- **Blue-green Deployment** -> Two environments (blue and green) are maintained. New changes are deployed to the blue environment, while users continue using green. After testing, traffic is switched to blue, minimizing downtime and allowing for easy rollback if issues arise.

- **Canary Deployment** -> Releases updates to a small user segment to monitor performance and gather feedback. If successful, the update is gradually rolled out to the rest of the users, minimizing risk.

- **Rolling Deployment** -> Incrementally replaces instances of an application with the new version, reducing downtime and allowing continuous availability.

- **A/B Testing** -> Different application versions are deployed to user segments to test performance, usability, and other metrics before a full rollout.

- **Feature flags** -> Specific features are toggled on or off for different user groups, allowing gradual release and testing in production.