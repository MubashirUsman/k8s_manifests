# Github Actions
Actions let you run **workflows**: workflows are process capable of running one or more **jobs**

Common community actions: 
+ build and push to docker registry
+ create aks cluster
 
## Job
A job can have multiple steps in a yaml list which are executed on a runner
```
my-checkout-job:
  name: my-checkout-job
  runs-on: ubuntu
  steps:
    - name: Checkout
      uses: actions/checkout@v3
```
The workflow is marked complete once all steps are completed successfully.
## Basic CICD
**CI** is merging of code in main branch 
**CD** is release of code to the environment

CI involves unit testing, linting, dependency scan, build artifact and code scanning.

## Core Components

Three main components
1. Workflow with triggers and name
2. Jobs with one or more steps
3. Steps

Jobs execute steps sequentially

run: npm install `for running shell commands`
GITHUB_TOKEN is used by actions to access the account

Actions version could be tag, branch or sha, @v2, @main, @a82400 
```
- name: Install dependencies
  run: npm install 
```


Writing custom javascript actions
  action.yml defines the interface of the action.
  inputs, outputs, runtime, entrypoint file (dist/index.js)
  when an action is called, that action is pulled and entrypoint is called.
  