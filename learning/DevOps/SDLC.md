# Software Development Process (SDLC)

The software development process consists of the following phases

### Requirement Gathering and Analysis

Information is collected such as
- product features
- user requirements
- current state of the market etc.

### Planning

Determines the cost and resources required form implementation of the product, and also the risk associated with it.

### Designing

Architects will design the software based on the inputs from previous phase. Architects will produce design documents which will act as roadmaps for developers.

### Development

This is where developers will write the software code based on the design

### Testing

Software will be tested by the software testers for any defects. It will be promoted to production only after fixing all the issues.

### Deployment

Software is deployed on the production environment so that users can start using the product.

### Maintenance

It is a balance between regular changes and uptime.



![[Pasted image 20240715133515.png]]

# Models in SDLC

There are different model in SDLC. You can understand these models as path or a roadways to reach the same destination as you choose a roadway based on different factors like cost,
risk and time taken to reach your destination. Some examples of different SDLC are:
### 1. **Waterfall**
In a waterfall model, each phase must be completed before the next phase can begin. Requirement completes then only planning begins, and then development starts. When everything is completed, all the features will be tested, and then maintenance phase starts. It is very difficult here to go back, and change something that was not well-thought out in the planning.
![[Pasted image 20240715134053.png]]

### 2. **Agile**
Each iteration could be two to four weeks. Demonstration of the features can be given to user after every iteration. and based on the feedback from user, new ideas can be injected in the next iteration. Demonstration of the features can be given to  user after every iteration, and based on the feedback from user, new ideas can be injected in the next iteration. 
Agile SDLC puts extra stress on the ops team. There will be regular code changes. These changes needs to be deployed on the servers so testers 
can conduct their testing. And this happens several times in a single iteration like that. You have several lacerations to go. Ops team is tired with regular deployment requests. There are clear instructions which causes the deployment failures. Ops team is also occupied with production support. They need to maintain system uptime all the time in-between these failures and fixes,
![[Pasted image 20240715134544.png]]

3. **Spiral**

4. **Big Bang** etc.


# DevOps
![[Pasted image 20240715135540.png]]

- Dev is Agile, all about regular and quick changes.
- Ops is ITIL-driven.(Information Technology Infrastructure Library),i.e. it provides stable environment for the product.
- There's a big wall of confusion in-between these two parties.
- A developer task their code over the wall and ops team responsibility is to deploy the core on the servers.
- Developers complain about delay in deployments. 
- Ops team complains about unclear instructions, and tossing their work over the wall.
To solve the issues  DevOps practices are used to automate the software development process by
- automation training and instruction to every team across the board.
- Automation of each and every task in code delivery process, like code build, code testing, software testing, infra changes, deployments and everything that comes along the way.




