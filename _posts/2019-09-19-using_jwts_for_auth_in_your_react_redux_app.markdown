---
layout: post
title:      "Using JWT's for auth in your react/redux app"
date:       2019-09-19 20:18:30 +0000
permalink:  using_jwts_for_auth_in_your_react_redux_app
---


I'm sure we can all agree that security is important in your app. Authenticating users not only makes your app trustworthy but also it kinda feels cool to be in control of it.

So now you are planning your app and are thinking of how to do auth and to keep a current user going. Before in the rails app you most likely used sessions to store a user_id on login and you check from there on every request. The problem is when you generate a new rails app with the --api flag you won't be able to use sessions without some tinkering.

JWT's will have a similar flow, you will generate a token on login and save it to localStorage, and to auth you check local storage for token and include it in the headers of your request:

											headers: {
																	"Authorization": token
																}

To logout you will just delete delete the token:

											localStorage.removeItem("token")
										
Nothing too crazy. If you feel like this could be a solution for you here is the gem and link to some more in depth instructions tailored for flatiron students:

											gem 'jwt'
											
								      https://levelup.gitconnected.com/using-jwt-in-your-react-redux-app-for-authorization-d31be51a50d2
											
Thank you, and enjoy!




