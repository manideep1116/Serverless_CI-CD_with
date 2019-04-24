# Serverless CI/CD with AWS

* As we know, serverless is fast becoming the new default compute model for many software projects.

* The attractive pay as you go pricing model, ease of deployment, rapid scaling capability and reduced ops overhead are very compelling advantages to any organisation shipping software.

* In essence serverless is a new abstraction of the infrastructure layer, a natural evolution from containerisation via new scheduling capabilities.

* Instead of worrying about provisioning virtual machines or scaling container infrastructures development teams can focus on the business.

* Serverless of course doesn’t mean no servers, simply that the responsibility of provisioning and maintaining those resources is no longer ours.

* While applications are moving to this new compute model, we’re often still left with some traditional infrastructure in the form of build servers and nodes.This remains a burden for ops due to having to perform OS patching, build server updates and managing fleets of build nodes as well as monitoring for performance and right-sizing both server and build nodes on an ongoing basis.

* Now, we create a serverless CI/CD pipeline on AWS using CodePipeline, CodeBuild and CloudFormation. This pipeline will be deploying a simple nodejs express application to lambda.
