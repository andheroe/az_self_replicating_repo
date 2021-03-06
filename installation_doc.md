## Installation of self_replicating_repo app

#### Prerequisites

1. Git and Github account
2. Python3
3. Heroku account and CLI (Check the instruction on how to register & get it below)
4. Github OAuth app (Check the instruction on how to create it below)

#### Register Heroku account and get Heroku CLI
We'll use Heroku to deploy the app live. By default they give free server that fully covers our needs here.
1. Register your account on [Heroku website](https://www.heroku.com/)  
2. Install Heroku CLI on your machine [Installation guide](https://devcenter.heroku.com/articles/heroku-cli)

#### Create Github OAuth app
The purpose of the app is to replicate app's repository on behalf of authorized user without asking for user's password.
Github provides ability to use OAuth apps to authorize users. 
Check the official documentation on how to create and use Github OAuth app. 
[Documentation](https://developer.github.com/apps/building-oauth-apps/creating-an-oauth-app/)  


#### Install the app locally

1. Clone the app's code to your machine.  
`git clone https://github.com/zhukandrey/self_replicating_repo`  
2. Install and activate venv  
`cd self_replicating_repo`  
`python3 -m venv venv`  
`source venv/bin/activate`  
3. Install required packages  
`pip install -r requirements.txt`  
4. Set environment variables with Github OAuth app GITHUB_CLIENT_ID & GITHUB_CLIENT_SECRET  
[How to set enviroment variables for Mac OS](https://medium.com/@youngstone89/setting-up-environment-variables-in-mac-os-28e5941c771c)   
[How to set enviroment variables for Linux](https://www.cyberciti.biz/faq/set-environment-variable-linux/)   
[How to set enviroment variables for Windows](http://www.dowdandassociates.com/blog/content/howto-set-an-environment-variable-in-windows-command-line-and-registry/)   
5. Run the app locally  
`flask run` 

#### Deploy the app to Heroku
1. Assuming we already logged in to Heroku CLI, create the new app on Heroku account  
`heroku apps:create <app_name>`  
When you create an app, a git remote (called heroku) is also created and associated with your local git repository.
2. Set environment variables with Github OAuth ID AND SECRET  
`heroku config:set GITHUB_CLIENT_ID=XXXXXXX`  
`heroku config:set GITHUB_CLIENT_SECRET=YYYYYYY`
3. Deploy the app to Heroku  
`git push heroku master`

#### Result
Now you can visit the app at the URL generated by its app name. As a handy shortcut, you can open the website as follows:  
`heroku open`