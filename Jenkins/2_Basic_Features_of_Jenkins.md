### What is Testing? 
- Testing is the process of evaluating a software product to identify any defects or errors. It is a critical component of software development that helps in ensuring that the software meets the requirements and specifications. Testing is performed at different stages of the software development lifecycle, and it can be automated or manual. Testing in Jenkins is one of the automated testing ways.

1. Unit test:
- involves testing individual components or units of the software product.
- It is usually performed by developers to ensure that each unit of the software works as expected.
- Unit tests are automated 
- Usually the first type of testing that is performed in the software development lifecycle.
2. Functional test
- involves testing the functionality of the software product.
- It is performed to ensure that the software meets the requirements and specifications.
- Usually automated
- Performed after the unit testing is complete.
3. Acceptance test
- Involves testing the software product to ensure that it meets the customer's requirements
- Usually performed by the customer or end user to ensure that the software meets their needs
- Can be manual or automated
- Usually the last type of testing that is performed in the software development lifecycle
4. Integration test
- Focuses on the integration of different components of a system
- Used to ensure that the components are working together as expected and that they are compatible with each other
- Typically written in a scripting language such as bash or groovy.
5. Performance test
- a type of testing that focuses on the performance of a system
- is used to ensure that the system is performing as expected and that it is meeting the performance requirements of the user
-  typically written in a scripting language such as bash or groovy
6. Security Test
- used to ensure that the system is secure and that it is meeting the security requirements of the user
- typically written in a scripting language such as bash or groovy


### Implementing testing in Jenkins
- Jenkins is an open source automation tool that can be used to automate the testing process.
- Jenkins can be used to automate unit testing, functional testing and acceptance testing.
- Jenkins can be integrated with different testing frameworks such as JUnit, Selenium and TestNG to automate the testing process.
- To implement testing in Jenkins, you need to create a Jenkins job that will perform the testing. The Jenkins job can be configured to run the test automatically whenever there is a new code commit. The test results can be published in the Jenkins dashboard and notifications can be sent to the development team of any errors or defects are identified. 

### Testing - Demo
1. First of all, we need to install Ant.
2. We need to link Jenkins with Ant
- Go Jenkins > Manage Jenkins > Global Tool Configuration > Ant > Ant installations
- ![image](https://github.com/NouhaThabet/Data-Engineer-Science-Notes/assets/17888203/bd88a172-17f0-4ff2-a467-ae5a18815a1e)
3. Create a new job Freestyle project "testing job"
- General > Select GitHub Project and put the URL
- Source Code Management > Git
- Again Paste repository URL + Credentials
- Verify the branch name
- Build Triggers > Build Environment > With Ant > Select Ant version
- Invoke Ant > Ant Version + Targets 
