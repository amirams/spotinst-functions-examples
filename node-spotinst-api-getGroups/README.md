# Get Elastigroups Serverless Function using Spotinst API 

This is a simple node project that allows you to connect to the Spotinst API and get current Elastigroups from your account.

### Prerequisites

You will need to have the serverless framework installed, your Spotinst credentials set up and you will need an API token, environment ID and account ID in order to run this project. 

First you will want to install the serverless framework onto your local machine using the terminal command

```
npm install -g serverless
```

Once this has finished downloading you will have to set up your credentials to link your local machine projects to your Spotinst console. To do this please follow the directions listed [here](https://serverless.com/framework/docs/providers/spotinst/guide/credentials/) This will generate a token which you will need in order to gain access to the Spotinst API so copy this somewhere for later use. 

You will also need your environment ID for your function. This can be found on the Spotinst console under the Serverless Functions tab. Select the application you wish to deploy this funciton to and locate the environment that you wish to use. Copy the environment ID and save this for later use

The last thing you will need is your account ID which can be found in the Spotinst console under user setting. Save this for later use. 

### Installing

First you will need to fork this repository and set it up on your local machine. Then you will need to install the serverless-spotinst-functions plugin as well as the request and the request-promise libraries by running this command inside the project repository:

```
npm install
```

Once this has been completed navigate to the handler.js file and input your token and account ID. Then you will need to navigate to the serverless.yml file and under environment add in the environment ID in the environment section.

## Deployment

Next you will want to deploy this function using this command:

```
sls deploy
```

The first time you run this command your new function will be created and linked to your Spotinst account under the environment that you specified. You can check this on the Spotinst Functions console. 

## Testing

To test if this is working use the command:

```
sls invoke -f getElastigroups
```

Or you can use the test feature on the Spoinst console. Either way the output to the console should be 'No new Elasitgroups' if you do not have any new Elasitgroups in the last hour. Or you will see 'New Group Found' with the groups ID if you do have a new Elastigroup within the last hour. If you have entered the wrong credentials you will get an error.

## Invoking 

For practical use, every Spotinst function is given a unique URL that will run the function every time the HTTPS request is made. 

## Optional

If you want you can set this function up to run on a schedule using the cron function in the serverless.yml file. Use the [cron function reference](https://crontab.guru/) for help on setting up your cron function. 


