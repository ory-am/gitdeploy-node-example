## Gitdeploy node example

This is a NodeJS example for [gitdeploy.io](https://gitdeploy.io) based on *NodeJS Chat under  (MIT License)*.

[![Deploy gitdeploy-node-example via gitdeploy.io](https://img.shields.io/badge/gitdeploy.io-deploy%20gitdeploy--node--example/master-green.svg)](https://www.gitdeploy.io/deploy?repository=https%3A%2F%2Fgithub.com%2Fory-am%2Fgitdeploy-node-example.git)

---

## Node.js Chat (MIT License)

A Node.js chat app using web sockets (socket.io)

##Run Local

Install all dependencies:

    npm install (you may need to prefix this with <sudo> if you're on Mac)

Run the app:

    node server.js

Then navigate to `http://localhost:3000`

##Sign up, and deploy to Nodejitsu

###Documentation

The documenation is available on the front page, under the sign up for free button: https://www.nodejitsu.com/getting-started/

Install the Nodejitsu Package

    npm install jitsu -g (you may need to prefix this with sudo for MAC OSX)

Register via the command line:

    jitsu signup (yes, you can sign up via the command line)

You will get a confirmation email with a command to input:

    jitsu users confirm [username] [confirmation-guid]

If you already registered, login with:

    jitsu login

After you confirm your email, you can login. The `confirm` command should prompt you to login.

Change the `subdomain` value in `package.json`, to reflect the target deploy URL:

    {
      "name": "nodejs-chat",
      [...],
      "subdomain": "nodejs-chat" <--- this value
    }

now deploy:

    jitsu deploy

And your app should be up on Nodejitsu.

##Signing up, and deploying to Heroku

###Documentation

From heroku.com, click "Documentation", then click the "Getting Started" button, then click "Node.js" from the list of options on the left, which will take you here: https://devcenter.heroku.com/articles/nodejs 

Install Heroku toolbelt from: https://toolbelt.heroku.com/

Sign up via the website without any credit card requirement.

Login using the command line tool:

    heroku login

Create your heroku app:

    heroku create

Git deploy your app:

    git push heroku master

Assign a dyno to your app:

    heroku ps:scale web=1

Open the app (same as opening it in the browser):

    heroku open

And your app should be up on Heroku.

##Signing up, and deploying to Azure

###Documentation

From windowsazure.com, click "Documentation", click "Developer Center", click "node.js", then click the "Learn More" button which will take you here:

http://www.windowsazure.com/en-us/develop/nodejs/tutorials/create-a-website-(mac)/ (on Mac, the link appears to be contextual)

Install the command line tools from here:

http://www.windowsazure.com/en-us/downloads/#cmd-line-tools 

for Windows, install the cross platform command line interface; not the powershell version.

From the command line, first download your publish settings triggering a website redirect:

    azure account download

After the `.publishsettings` file download, you import it:

    azure acount import %pathtofile%

Next create the site, with a git backed repository:
    
    azure site create %uniquesitename% --git

Deploy the site:

    git push azure master

Create a report of your websites:

    azure site list

And your app should be up on Azure.
