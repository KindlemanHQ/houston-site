---
title: With Launchpad
layout: docs
---

The easiest way to get started is to create a new project with Launchpad, our Rails starter template.  It will include everything you need to get going. 

1. Download the template
````bash 
git clone git@github.com:KindlemanHQ/launchpad.git
````

2. Create your rails app
````bash
  rails new yawebsite -a propshaft  -d sqlite3  -m launchpad/template.rb
````

3.  Watch it build all your things!

Once done, start your site in the usual way and check out all your functionality. 

````bash
bin/dev
````

4.  You will want to create a site_admin user, we do not do that automatically for security.  Sign up using the site links and then update your user to be site_admin in the console.
<br><br>

![Sign up using the site links](/assets/images/signup.webp)


````bash
rails c
u = User.last
u.site_admin = true
u.save
````

And now you can follow the link in the user drop down to go to /admin and see the admin functionality. 


![Site Admin](/assets/images/siteadmin.webp)