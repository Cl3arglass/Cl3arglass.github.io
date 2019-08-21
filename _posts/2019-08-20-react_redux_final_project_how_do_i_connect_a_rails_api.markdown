---
layout: post
title:      "React Redux Final Project: How do I connect a rails api?"
date:       2019-08-21 01:24:44 +0000
permalink:  react_redux_final_project_how_do_i_connect_a_rails_api
---


If you are reading this you are most likely at or nearing your final project and that deserves a "congrats!". 

Connecting a rails api as your backend is fairly easy. There are just a few configurations needed to allow the api to be comunicated with.

Right off the bat I would recommend having a parent folder on your local machine that will contain two seperate directories; your react app front end, and your rails api backend. This will set you up to have a seperate git repository for each directory.

Now after you have created yor rails api with "rails new api-name --api" you will nee to activate the gem 'rack-cors'. Using "--api" will make an app without views and even block further views from being created by generators.

Next in config/initializers/cors.rb comment in the code there. This will allow you to talk to your api outside of rails server. This is also where you can control requests. To allow all requests you can use * for origins and resource. At this time you might want to change the port your rails server is on in config/puma.rb to "3001" so you can easily have your front and back end servers running at the same time on your local machine.

That's pretty much it, once you have your react/redux app ready with thunk you can make async fetch requests they will look something like "http://localhost:3001/api/login" or however you set up your routes in the backend.
