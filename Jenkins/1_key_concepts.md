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
1. Freestyle Project
2. Maven Project
3. Pipeline
4. Multi-configuration Project
5. Multi-branch pipeline

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



