It is an automated process in DevOps which generates software and its features quickly and efficiently.

### Process
- Developers write several lines of code while creating a software working in a team. 
- It's an ideal practice to store all this code at a centralized place. This centralized repository is called a version control system like GitHub.
- Everyday developers will pull and push code such repositories several times in a day. 
- So code changes or code commit happens continuously. 
- This code will be moved to build server on build server. 
- This code will be build, tested and evaluated, which generates the software, or we call it artifact at this stage. 
- From repository It will be shipped to servers for further testing.
- After deploying this artifact on the servers, software testers can conduct further testing, and once they approve, it can be shipped to production servers. 
- So the code is getting merged into the repository, but not really getting integrated. 
- The solution to this is a very simple and a continuous process after every single commit from the developers, the code should be built and tested, so no waiting and collecting all these codes with bugs.
- But then developer commits several times in a day, so it's not humanly possible to do a build & release several times in a day. 
- The manual process so that's simple, just automated. So when the developer commits any code and automated process, will fetch the code, build it tested and send a notification if there is any failure. 
- As soon as the developers receives a failed notification, he or she will fix the code and commit it again. So again, build and test new changes, if it's good, then it can be versioned and stored in a software repository. And it's all automated


This automated process is called **continuous integration**, or **CI** in short. The goal of CI is to detect defects at a very early stage, so it does not multiply.