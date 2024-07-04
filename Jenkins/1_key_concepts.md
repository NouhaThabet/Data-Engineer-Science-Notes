### What are Jenkins Jobs? 
- The main element of Jenkins.
- A Jenkins job is considered a Jenkins project and every job could have some smaller steps called builds.
- They are used to build, test, deploy, and monitor software projects and can be configured to run on a schedule triggered by an event or manually initiated.
- They are highly customizable and can be written using various programming languages (python,Groovy)

Jenkins jobs are used for :
1. Build/Deploy: Jenkins jobs can be used to compile code and build packages, as well to run unit tests and integration tests. For deployments, Jenkins jobs can be used to deploy software packages to production, as well as to rollback packages in the event of a failure.
2. Run Tests
3. Monitor
4. Updates
5. Maintanace
6. Automation of repetitive process : generating reports or sending emails on a schedule, sending notofications when a job succeed or fail.
7. Additionnaly: Jenkins jobs can be configured to run in parallel, configured to have multiple stages.

### Types of Jenkins Jobs: 
**1. Freestyle Project**: is a type of project that allows users to configure and customize their own build process. It is the most commonly used project type in Jenkins and is the most flexible and extensible of all the project types. With the freestyle project, users can define their own build steps, set up triggers, and configure various options such as source code management, build triggers, built environment, build steps, post build actions and more. It is also a great choice for more control over the builds and for automation and continuous integration and continuous delivery.

**2. Maven Project**: Maven projects and Jenkins are projects that are built using maven. Maven is a build automation tool used primarily for Java projects. It is used to manage the build, reporting, and documentation of a project based on the concept of a Project Object Model, POM. It is used to define the project structure, dependencies, builds, and test management. The maven project job type helps build maven projects. However, Jenkins does not provide it as part of the core functionality. As such, it requires you to install the maven integration plugin. Jenkins can be used to build maven projects by using the maven plugin. This plugin allows Jenkins to execute maven goals and manage the build process. It also allows Jenkins to monitor the build process and report the results. 

**3. Pipeline:** Jenkins pipeline projects are a great way to automate your software delivery process. They allow you to define a series of steps that must be completed in order to successfully deliver your software. This includes everything from building and testing your code to deploying it to production. They also allow you to define triggers that will start the pipeline when certain conditions are met. This allows you to automate the process of delivering your software. 

**4. Multi-configuration Project:** This is the type of project that allows you to run the same job multiple times with different configurations. This is useful when you need to run the same job with different parameters, such as different versions of software, different operating systems, or different hardware configurations. If you are working on a project requiring multiple configurations, you prefer to use the multi-configuration project option.

**5. Multi-branch pipeline:** is a type of pipeline that creates a set of pipeline projects according to detected branches and one SCM repository. It allows for the automatic creation of multiple branches of a project, each with its own Jenkins file. This type of pipeline is useful for projects that have multiple branches, such as a development branch, a staging branch, and a production branch. With a multi-branch pipeline, Jenkins can automatically detect changes in each branch and trigger a build for each branch. It allows for more flexibility in the build process. For example, developers can specify different build steps for each branch, such as running tests or deploying to different environments. This allows for more control over the build process and ensures that the correct steps are taken for each branch.

### Jenkins Project Types Comparison

| Feature | Freestyle Project | Maven Project | Pipeline | Multi-configuration Project | Multi-branch Pipeline |
|---------|--------------------|---------------|----------|-----------------------------|-----------------------|
| **Definition** | Basic project with a simple configuration for building software. | Specialized project for building Maven-based projects. | Project that defines build process with a Jenkinsfile using Groovy DSL. | Project allowing different configurations (e.g., environments, platforms). | Pipeline project supporting multiple branches with separate Jenkinsfiles. |
| **Configuration** | Configured through the Jenkins web UI. | Configured through the Jenkins web UI, with Maven-specific options. | Configured via a Jenkinsfile in Groovy, stored in source control. | Configured through the Jenkins web UI with matrix configuration. | Configured via a Jenkinsfile in each branch, stored in source control. |
| **Use Case** | Simple builds, shell scripts, or batch commands. | Maven-based projects needing specific build and deployment steps. | Complex build processes, CI/CD pipelines, scriptable steps. | Projects requiring different configurations for testing or deployment. | Multi-branch projects, such as Git branches with separate pipelines. |
| **Source Control Integration** | Basic integration, manual setup for SCM polling. | Integrated with Maven SCM, SCM polling supported. | Strong integration with SCM, Jenkinsfile stored in the repo. | Basic integration, manual setup for SCM polling. | Strong integration with SCM, Jenkinsfile per branch. |
| **Pipeline as Code** | No | No | Yes | No | Yes |
| **Parallel Execution** | Limited | Limited | Yes, with stages and parallel steps. | Yes, across different configurations. | Yes, across different branches. |
| **Flexibility** | Low | Medium | High | Medium | High |
| **Build Triggers** | SCM polling, schedule, manual. | SCM polling, schedule, manual. | SCM polling, webhooks, schedule, manual. | SCM polling, schedule, manual. | SCM polling, webhooks, schedule, manual. |
| **Plugins Required** | Minimal, depending on build steps. | Maven Integration Plugin. | Pipeline Plugin, SCM plugins. | Matrix Project Plugin. | Pipeline Plugin, Branch Source Plugin. |

### What are Builds? 
A build is an instance of a job that performs a specific task, such as building, testing, deploying, or running your code. For example, you can have a build that compiles your Java code using Maven, another build that runs unit tests using JUnit, and another build that deploys your application to a Kubernetes cluster using Help. To create a build, you need to have a job first. A job is a collection of steps that define your pipeline. 

### Builds - Demo 
1. Create a simple job
- create a job job-0001 which is a freestyle project
- we create a simple shell : `echo "Hello"`
- Jenkins store the files and the jobs in the *var/lib* directory
- `cd /var/lib/jenkins`
- ![image](https://github.com/NouhaThabet/Data-Engineer-Science-Notes/assets/17888203/5a68f606-752c-4285-a491-a01f867f93c3)
- We don't find anything in the workspace because there is no job yet in the jenkins environment.
- Once we create the job we will get a directory there with the name of the job
- For example I will save and start building this job, I will do build now to create our first build. And as you can see it was successful build, and if I do LS again, I will find the job directory. If I do CD job 001, I will find the file of the output and if I do cat message, it's sensitive to capital case. If I do cat message as you can see here, I got the output of this file.
2. Create a Second job that triggers the first one
- Create a job 002
- ![image](https://github.com/NouhaThabet/Data-Engineer-Science-Notes/assets/17888203/2d2d1e63-e3e7-498c-9684-d8269434aeb4)
- ![image](https://github.com/NouhaThabet/Data-Engineer-Science-Notes/assets/17888203/0df9891e-b507-42fd-ac5e-218bd1bf7971)
- ![image](https://github.com/NouhaThabet/Data-Engineer-Science-Notes/assets/17888203/53a9f113-3ecd-4b6c-9e8b-aaafee07be6e)
- ![image](https://github.com/NouhaThabet/Data-Engineer-Science-Notes/assets/17888203/9bfe63e9-cc8d-4b79-8dff-eb0975b425ed)
- Here we find the jobs under job 001 and it can be more than one job and can be a large network of downstream or upstream projects, according to the size of the project we working on. 
- ![image](https://github.com/NouhaThabet/Data-Engineer-Science-Notes/assets/17888203/bed6a592-e79d-4403-9605-5deab031d9b2)


### Source Code Management Concept
- SCM in Jenkins stands for source code management, which is the practice of managing and tracking changes to software code. It provides way for developers to collaborate on code and maintain a version history of their work.
  
1. Benefits of using SCM
   - It allows developers to track changes made to code over time
   - Maintain multiple versions of the codebase, and work on the same codebase simultaneously.
   - It is used to manage the codebase, and Jenkins uses this codebase to automate the build and 
   deployment process.
   - It also provides a backup of previous versions of the codebase in case there is a need to 
    revert to an earlier version.

2. Incremental Update in SCM
- Incremental Update is a technique used to update an existing copy of the codebase with changes made by other developers.
- It only downloads the changes made to the codebase since the last update, making it faster than a Clean Checkout.
- It is useful when you want to keep your codebase up to date with the latest changes, but you don't want to download the entire codebase every time you make a change.
- If there are conflicts between the changes made by different developers, it can lead to errors and delays in the development process.

3.Clean Checkout in SCM
- Clean Checkout is a technique used to download an entire copy of the codebase from the source code repository.
- It downloads all the files and directories in the codebase, including the latest version of the source code.
- Clean Checkout is useful when you want to start working on a new project or when you need to create a new copy of the codebase.
- It ensures that you have a complete and up to date copy of the codebase to work with.
- However, Clean Checkout can be slower than Incremental Update since it downloads the entire codebase every time you make a change. It can also take up more disk space on your computer.

4. Incremental Update or Clean Checkout
-  If you're working on a small project with a limited number of developers, Incremental Update may be the best option for you. It's faster and more efficient.
-  However, if you're working on a larger project with many developers, Clean Checkout may be a better choice. It ensures that everyone has the same copy of the codebase to work with, and reduces the risk of conflicts.

5. Important Concept :
- Version Control Systems (VCS) : VCS is a software tool that helps manage changes to the codebase. It tracks all changes made to the code, allowing developers to revert to previous versions if necessary. There are two types of VCS, *centralized* and *distributed*. *Centralized VCS* stores the code in a *central repository*, while *distributed VCS* allows each developer to have a *local copy of the codebase*.
- Branching and Merging
- Pull Requests and Code Reviews
- Continuous Integration and Deployment






