---
title: Media Library
layout: docs
---

# Media Library

Add media Management to your tractor.rb initializer

````ruby
 unless Tractor::Engine.config.sidebar_content_items.any? { |item| item[:name] == "Media" }
    Tractor::Engine.config.sidebar_content_items << {
      name: "Media",
      icon: "bi-images",
      path: "/admin/medias"
    }
  end
````  