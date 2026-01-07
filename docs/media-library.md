---
title: Media Library
layout: docs
---

# Media Library

Add media Management to your config/initializers/houston_cms.rb  initializer

````ruby
 unless HoustonCms::Engine.config.sidebar_content_items.any? { |item| item[:name] == "Media" }
    HoustonCms::Engine.config.sidebar_content_items << {
      name: "Media",
      icon: "bi-images",
      path: "/admin/medias"
    }
  end
````  

Restart the dev server and go to the Media area. You can now add Media using the simple forms. 

![Create Form](/assets/images/media-create.webp)

![Edit Media Form](/assets/images/media-edit.webp)


You can then use these Media in other areas in the CMS.  For example the markdown fields allow you to select from the media list.  



![insert Media](/assets/images/insert-media-2.webp)