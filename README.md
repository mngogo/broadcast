broadcast
=========

Broadcast is a simple Meteor app for syncing presentations on the web in realtime. [Click here to learn more about the story behind Broadcast](https://www.youtube.com/watch?v=ydLFWnGPnew&list=UU3fBiJrFFMhKlsWM46AsAYw).

# Setup

## Sign Up for 3rd Party Services

You'll need to create an account for all of these free services:

- Box View API key: http://box.com/developer_signup
- Kadira: https://ui.kadira.io/sign-up?plan=free
- Google Analytics: https://www.google.com/analytics/

## Install Meteor

If you haven't installed Meteor yet, run this command:

	$ curl https://install.meteor.com | /bin/sh

## Clone the repo

Run:

    $ git clone https://github.com/seanrose/broadcast.git
    $ cd broadcast

## Add settings.json

You'll need to add a `settings.json` file at the root with the API keys from all of the services you signed up for:

	{
	    "box": {
	        "token": "API key for Box View"
	    },
	    "kadira": {
	    	"appId": "Kadira App ID",
	    	"appSecret": "Kadira App Secret"
	    },
	    "public": {
	        "filepicker": {
	            "key": "filepicker API key"
	        },
	        "ga": {
	            "id": "Google Analytics tracking ID"
	        },
	        "typekit": {
	            "url": "Typekit URL (not used yet)"
	        }
	    }

	}

## Install Packages

Install the required packages:

    $ meteor update

## Set Up Box View Webhooks

Broadcast uses webhooks from Box View to load converted presentations immediataely and create an ultra fast experience. To set up Box View webhooks, email api@box.com with your **API key** and the URL that they need to send webhooks to, which by default is `https://{{ your app name }}/webhook`

## Running the App Locally

From the root of the project, after configuring `settings.json`, run this command:

	$ meteor --settings settings.json

## Deploying the App to meteor.com

Decide on a name for your app, and run this command from the root of your broadcast directory:

    $ meteor deploy {{ your app name }} --settings settings.json

You may want to create a file named `deploy.sh` at the root of your project with this command and other deployment configurations to make deploying easier.

## For More Info About Meteor

http://docs.meteor.com/
