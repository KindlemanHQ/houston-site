---
title: With Launchpad
layout: docs
---

The easiest way to get started is to create a new project with Launchpad, our Rails starter template.  It will include everything you need to get going. 



gem "tractor", github: "asecondwill/tractor-rails", tag: "v0.1.15"
gem "tractor-menus", github: "asecondwill/tractor-menus", tag: "v0.1.0"

rails generate tractor:install 
rails db:migrate

make sure user responds to site_admin
add @import "admin_helpers"; to application.scss


add gem "marksmith"
gem "name_of_person"

  add  to user
  def full_name
    if first_name
      name.familiar
    else
      email
    end
  end

  add ransack stuff for users
  add debug to user

  
