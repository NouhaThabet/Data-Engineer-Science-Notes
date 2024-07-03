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
1. Freestyle Project: is a type of project that allows users to configure and customize their own build process. It is the most commonly used project type in Jenkins and is the most flexible and extensible of all the project types. With the freestyle project, users can define their own build steps, set up triggers, and configure various options such as source code management, build triggers, built environment, build steps, post build actions and more. It is also a great choice for more control over the builds and for automation and continuous integration and continuous delivery.
2. Maven Project: Maven projects and Jenkins are projects that are built using maven. Maven is a build automation tool used primarily for Java projects. It is used to manage the build, reporting, and documentation of a project based on the concept of a Project Object Model, POM. It is used to define the project structure, dependencies, builds, and test management. The maven project job type helps build maven projects. However, Jenkins does not provide it as part of the core functionality. As such, it requires you to install the maven integration plugin. Jenkins can be used to build maven projects by using the maven plugin. This plugin allows Jenkins to execute maven goals and manage the build process. It also allows Jenkins to monitor the build process and report the results. 
3. Pipeline: Jenkins pipeline projects are a great way to automate your software delivery process. They allow you to define a series of steps that must be completed in order to successfully deliver your software. This includes everything from building and testing your code to deploying it to production. They also allow you to define triggers that will start the pipeline when certain conditions are met. This allows you to automate the process of delivering your software. 
4. Multi-configuration Project : This is the type of project that allows you to run the same job multiple times with different configurations. This is useful when you need to run the same job with different parameters, such as different versions of software, different operating systems, or different hardware configurations. If you are working on a project requiring multiple configurations, you prefer to use the multi-configuration project option.
5. Multi-branch pipeline: is a type of pipeline that creates a set of pipeline projects according to detected branches and one SCM repository. It allows for the automatic creation of multiple branches of a project, each with its own Jenkins file. This type of pipeline is useful for projects that have multiple branches, such as a development branch, a staging branch, and a production branch. With a multi-branch pipeline, Jenkins can automatically detect changes in each branch and trigger a build for each branch. It allows for more flexibility in the build process. For example, developers can specify different build steps for each branch, such as running tests or deploying to different environments. This allows for more control over the build process and ensures that the correct steps are taken for each branch.

# Jenkins Project Types Comparison

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



