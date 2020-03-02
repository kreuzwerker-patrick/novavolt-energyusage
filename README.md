# novavolt-energyusage

# basic setup

## NPM (NodeJS)
prequisite is to have NodeJS and NPM installed

## install npm packages (e.g. serverless framework)
``
npm install 
``


# test examples

## in CI/CD using serverless mocha framework

### create new test for function
``
sls create test -f getZapCloudData
``

### run tests for a function
``
sls invoke test -f getZapCloudData
``

Result:
``
Serverless: Tests being run with nodejs13.8,  service is using nodejs10. Tests may not be reliable.


  getZapCloudData
    ✓ implement tests here


  1 passing (5ms)

``

### run all tests for a stage
``
sls invoke test --stage dev
``




## using serverless framework
### local

``
sls invoke local -f getZapCloudData
``

Result:
``
{
    "statusCode": 200,
    "body": "{\n  \"message\": \"Go Serverless v1.0! Your function executed successfully!\",\n  \"input\": {}\n}"
}
``

further documentation here:
https://serverless.com/framework/docs/providers/aws/cli-reference/invoke-local/


### remote
``
sls invoke -f getZapCloudData
``

Result:
``
{
    "statusCode": 200,
    "body": "{\n  \"message\": \"Go Serverless v1.0! Your function executed successfully!\",\n  \"input\": {}\n}"
}
``
further documentation here:
https://serverless.com/framework/docs/providers/aws/cli-reference/invoke/




## using lambda-local
``
lambda-local -l get-data-zapcloud -h getData -e get-data-zapcloud.js 
``

Result:
``
info: START RequestId: fa0f2d06-46ee-a7d2-0fd3-4dfb47351a37
info: End - Result:
info: {
	"statusCode": 200,
	"body": "{\n  \"message\": \"Go Serverless v1.0! Your function executed successfully!\",\n  \"input\": {}\n}"
}
``

further documentation here:
https://www.npmjs.com/package/lambda-local#about-cli


# deployment examples

## deploy DEV
``
sls deploy --stage dev -v  
``

## remove deployment
``
sls remove
``

