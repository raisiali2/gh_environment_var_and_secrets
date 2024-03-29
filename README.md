# section 6: using environment variables & sectrets
environment variables are the variables that define dynamically to implement in dynamic environment, like it might be   
variable such as db username and password that change for different user.
## how we can provide values for env vars?
- we can define env vars workflow-level or job-level
- workflow-level: is such as db-name that will be the same for all the jobs
- job-level: variables that we want to use only in test-level-job
## creating database & using database environment variables values
for these created mongodb and provided all the values of env vars from ther.
## using env vars in code & workflow
env variables are needed in a lot of workflows to inject values as in the test



## what is environment variables & and how can we use it?
## what is secret & and how can we use it ?
the information like username, userpassword they must not expose in the github, because when someone get access to 
our github they can see them and access them, so in this case we need to put them either in organization lever or repository secret action.  
in the code use github expression syntax.  
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
