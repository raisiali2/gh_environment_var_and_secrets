# section 6: using environment variables & secrets
environment variables are the variables that define dynamically to implement in dynamic environment, like it might be variable such as db username and password that change for different user.
## how we can provide values for env vars?
- we can define env vars workflow-level or job-level
- workflow-level: is such as db-name that will be the same for all the jobs
- job-level: variables that we want to use only in in job-level like for only test-job
## creating database & using database environment variables values
for these created mongodb and provided all the values of env vars from there.
## using env vars in code & workflow
env variables are needed in a lot of workflows to inject values as in the test

## what is environment variables & and how can we use it?
## what is secret & and how can we use it ?
the information like username, user password they must not expose in the github, because when someone get access to our github they can see them and access them, so in this case we need to put them either in organization lever or repository secret action.  
in the code using github expression syntax.  
inside that for passing secret use `secrets context object`.  
after that if you run github no one can see the values.
## utilizing repository and job specific environment?
there are two ways to add variable in repo
1. add in repository workflow-level
2. create environment for a specific job and add variable to the created environment 
   then use `environment:` keyword to use this specific job-level environment variable 
   example:
   jobs:
      test: 
         environment: testing
         env:
         # this access the secrets that stored for this environment specific secrets and not the general repo secret
# module summary
![alt text](image.png)
## environment variables
Used to inject dynamic values in your code for example the name of database or all the use them inside of your workflow definition files as the below. the environment variables are different from workflow to workflow that you can define them in
- can be defined on workflow, job- or step-level.
these env vars are then automatically provided to the code that's executing on your workflow-job runner.
and the value of env vars are also available inside your workflow definition file.
for example:
you can interpolate them when 
- running command
- or using env context object to get access to the env variables
  
## secrets
- some dynamic values should not be exposed anywhere
- examples: database credentials, api keys etc.
- secrets can be stored on repository-level or via environments and for organization in organization level
- secrets can be referenced via the secret context object
  
## github actions environments
- jobs can reference different github actions environments
- environments allow you to set up extra protection rules
- for example: executions of some jobs under certain circumstances
- you can also store secrets on environment-level
  