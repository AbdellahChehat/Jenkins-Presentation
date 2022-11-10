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


