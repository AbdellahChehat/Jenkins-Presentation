## What is CI/CD
- CI/CD is a method to frequently deliver apps to customers by introducing automation into the stages of app development. The main concepts attributed to CI/CD are continuous integration, continuous delivery, and continuous deploymen

### Continuous Integration
- Requires developers to share code into the share repository several times a day, the code is verified by a automated build and here they check for bugs and manage how these will be fixed.
- Code is pushed to github branch where is it analysed and tested
- Some of the tests run include:
    - Unit testing – tests individual units of the code
    - Validation testing – checks the software satisfies the criteria of the client 
![ci](https://user-images.githubusercontent.com/115226294/201149108-ed31ee1c-f5a0-4565-8433-c05f97f8760f.png)

### Continuous Development
 - It's an extension of continuous integration to make sure that you can release new changes to your customers quicker in a much more sustainable method. So on top of your continuous integration, you also automated your release process and can deploy you application at any point of time by clicking a button. Deployment will have to be done manually but that can also be done automatically

### Continuous Deployment - CDE
- This goes one stage futher than Continuous Delivery by deploying the actual application online automatically, so each change that passes all the stages of your production pipeline is released to your customers, there is no human interaction so this lowers the chance for human error, and even one failed test will prevent the new change being deployed to production.

### Differences
- CD and CDE are very similar however there is 1 difference between the 2 prosesses. On continuous delivery the integration is automatic but you must manually deploy the application whereas in continuous deployment the whole process is automated so it integrates, tests and deploys it automatically.
![cicd1](https://user-images.githubusercontent.com/115226294/201148877-c492c48a-ca07-42f2-82e3-10bec872dd86.png)
![cd diff 1](https://user-images.githubusercontent.com/115226294/201148895-b79c0efc-4067-4921-950c-87cf57f0f24e.png)

### Webhooks
- A Webhook is a mechanism to automatically trigger the build of a Jenkins project in response to a commit pushed to a Git repository.
- This essentially means that you get the data immediately after it is pushed rather having to set up frequent pulls to get it in real time.

## What is Jenkins?
- Jenkins is an open source automation tool written in Java programming language that allows continuous integration.

- Jenkins builds and tests our software projects, which continuously making it easier for developers to integrate changes to the project, and making it easier for users to obtain a fresh build.

- It also allows us to continuously deliver our software by integrating with a large number of testing and deployment technologies.

- Jenkins offers a straightforward way to set up a continuous integration or continuous delivery environment for almost any combination of languages and source code repositories using pipelines, as well as automating other routine development tasks.

- With the help of Jenkins, organizations can speed up the software development process through automation. Jenkins adds development life-cycle processes of all kinds, including build, document, test, package, stage, deploy static analysis and much more.

- Jenkins achieves CI (Continuous Integration) with the help of plugins. Plugins is used to allow the integration of various DevOps stages. If you want to integrate a particular tool, you have to install the plugins for that tool. For example: Maven 2 Project, Git, HTML Publisher, Amazon EC2, etc.

- For example: If any organization is developing a project, then Jenkins will continuously test your project builds and show you the errors in early stages of your development.

- Possible steps executed by Jenkins are for example:

   - Perform a software build using a build system like Gradle or Maven Apache
   - Execute a shell script
   - Archive a build result
   - Running software tests

   ## What are Jenkins Stages

   ![image](https://user-images.githubusercontent.com/97250268/201118379-527ec3a3-05f8-4abb-ad4c-29d22abe31ff.png)
   
   - In a Jenkins Pipeline, every job has some sort of dependency on at least one or more jobs or events.

   ![image](https://user-images.githubusercontent.com/97250268/201120938-afee9c6a-b198-4c4d-99b4-1b9f9827babe.png)

   - The above diagram represents a continuous delivery pipeline in Jenkins. It contains a collection of states such as build, deploy, test and release. These jobs or events are interlinked with each other. Every state has its jobs, which work in a sequence called a continuous delivery pipeline.
  
   - A continuous delivery pipeline is an automated expression to show your process for getting software for version control. Thus, every change made in your software goes through a number of complex processes on its manner to being released. It also involves developing the software in a repeatable and reliable manner, and progression of the built software through multiple stages of testing and deployment.
  
    ## How does Jenkins Benefit the Buisness
    
- With Jenkins, you’ll get a lot of help. As you can see, it is the most widely used open-source server, therefore you will receive agile teams from all over the world to help you with your problems.
- The users encounter a variety of problems along the way. Such issues are quickly resolved, allowing the software to remain in a state where it may be released at any moment with complete confidence.
- The majority of the integration work is automated. As a result, there are fewer integration issues. This also helps to save money and time during the project’s path.
- The coding problems can be detected as soon as feasible by the engineers. This prevents them from having to deal with large-scale, error-prone integrations.
    
  ## Who is using Jenkins and CICD in the industry
  - More than  60,000 companies  use Jenkins. The companies using Jenkins are most often found in United States and in the Information Technology and Services industry. Jenkins is most often used by companies with 50-200 employees and 1M-10M dollars in revenue
  
  ![image](https://user-images.githubusercontent.com/97250268/201127306-81fd065a-7ce5-45c0-9a73-64674459297e.png)
  
  ![image](https://user-images.githubusercontent.com/97250268/201128871-30d8aaee-941d-4fc2-b058-39f5cb3c968c.png)

 ### Execute Shell script for the job to copy code to EC2 instance
 ```
 git pull origin main # To pull the code from GitHub
ls
rsync -avz -e "ssh -o StrictHostKeyChecking=no" app ubuntu@54.170.194.47:/home/ubuntu # This command copies code from github to the EC2 instance
ssh -A -o "StrictHostKeyChecking=no" ubuntu@ec2-54-170-194-47.eu-west-1.compute.amazonaws.com << EOF # To avoid the prompt when SSH into EC2 instance
ls
sudo killall -9 node # Kill all the processes running
cd app
npm install
nohup node app.js > /dev/null 2>&1 & # To run app in the background
EOF
 
 ```

