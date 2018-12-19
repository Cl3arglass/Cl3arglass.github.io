---
layout: post
title:      "Github Oauth: keep it secret"
date:       2018-12-19 22:18:44 +0000
permalink:  github_oauth_keep_it_secret
---


If you wish to get the Github authentication part working you will need to create a key using Github. From your Github profile, go to settings then onto developer settings. Click new Oauth app. For Authorization callback URL enter https://localhost:3000/auth/github/callback. After set up you will be given key and secret. In the house-plant app, go to config/initializers/omniauth.rb, and paste the ID and Secret into their spots like so:

GITHUB_KEY: XXXXXXX GITHUB_SECRET=XXXXX

But if you want to keep your ID and SECRET a secret in omniauth.rb leave GITHUB_KEY and GITHUB_SECRET as 'GITHUB_KEY' and 'GITHUB_SECRET' in the env brackets. Then we can create a secrets.yml file to store the real key and secret. From there place: 

    config_files = ['secrets.yml']

    config_files.each do |file_name|
      file_path = File.join(Rails.root, 'config', file_name)
      config_keys = HashWithIndifferentAccess.new(YAML::load(IO.read(file_path)))[Rails.env]
      config_keys.each do |k,v|
        ENV[k.upcase] ||= v
      end
    end
		
in your application.rb file into your app module. Lastly add your secrets file to your gitignore file so that your secret and key stay hidden from the public on github.

Enjoi
