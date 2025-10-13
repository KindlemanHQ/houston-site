---
title: Getting Started
layout: docs
---

# Getting Started

## 1. Create a new rails app, if you dont have one already.

````bash
> rails new huston-demo --database=sqlite3 --asset-pipeline=propshaft --javascript=importmap
> bin/rails dartsass:install
````

## 2.  Add huston, devise to your Gemfile.
````ruby
gem "tractor", github: "asecondwill/tractor-rails", tag: "v0.1.8"
gem "devise"
````

## 3. Bundle 
````bash
> bundle
````

## 4.  Run the install scripts
````bash
> rails generate devise:install
> rails generate devise User
> rails generate tractor:install 
> rails generate simple_form:install --bootstrap
# make sure you user responds to site_admin and name fields
> rails generate migration AddSiteAdminToUsers site_admin:boolean
> rails generate migration AddFirstNameToUsers first_name:string      
> rails generate migration AddLastNameToUsers last_name:string    
> rails generate migration AddTimeZoneToUsers time_zone:string   
  (edit the migration to default to your location)
> rails generate migration AddDebugToUsers debug:boolean
> (edit the migration to default to false)
> rails db:migrate

````

## 5. Create an Admin User
````bash
> rails c
User.create(email: 'buzz@example.com', password: 'DemoPassword123!', site_admin: true, debug: true)
````

## 6. Make sure User responds to full_name
````ruby
def full_name
  "#{first_name} #{last_name}"
end  
````

## 7.  Setup Sass files. 
````sass
# application.scss
@import "admin_helpers";
````

## Wrap up
And that's it.  Use the standard devise screens to sign in - eg at [http://localhost:3000/users/sign_in](http://localhost:3000/users/sign_in).



Next, lets [Add Snippets](/docs/snippets)

