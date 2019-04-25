# Serverless CI/CD with AWS

* As we know, serverless is becoming the new default compute model for many software projects.

* The attractive pay as you go pricing model, ease of deployment, rapid scaling capability and reduced ops overhead are very compelling advantages to any organisation developing software.

* Serverless is a new abstraction of the infrastructure layer, a natural evolution from containerisation via new scheduling capabilities.

* Instead of worrying about provisioning virtual machines or scaling container infrastructures development teams can focus on the business.

* Serverless of course doesn’t mean no servers, simply that the responsibility of provisioning and maintaining those resources is no longer ours.

* While applications are moving to this new compute model, we’re often still left with some traditional infrastructure in the form of build servers and nodes.This remains a burden for ops due to having to perform OS patching, build server updates and managing fleets of build nodes as well as monitoring for performance and right-sizing both server and build nodes on an ongoing basis.

* Now, we create a serverless CI/CD pipeline on AWS using CodePipeline, CodeBuild and CloudFormation. This pipeline will be deploying a simple lambda function.

---------------------------------
Basic Serverless Architecture:
We use API gateway and Lambda.

API Gateway: It will have resources and HTTP methods configured and each resource will be pointed to backend lambda function which provides response. So,Lambda function can be configured to work with other AWS services our own custom code to provide a required response to the API gateway. End users can access gateways either with URL or through route53.


--------------------------------------

Serverless Application Continous Deployment Workflow.

--> First end users will develop lambda functions in Node.js or Python and push them to git repo or CodeCommit.
--> We have two files required for this project. One is 'Sam Template' which basically defines our lambda function and API gateway and will be similar to Clouformation template with minor changes.Second one is 'Buildspec' which converts our samTemplate to cloudformation template.

-->After pushing these files, pipeline will be automatically triggered and these files are saved in S3 bucket and a Codebuild is triggered to convert this samtemplate file to cloudformation template. This template will have details about API gateway and Lambda. With this converted template a change set is created.

--> And then there will be manual approval to check the pipeline and approve.

-->Once approved Pipeline will excute change set which creates our lambda function and API gateway.
