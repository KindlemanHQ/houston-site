---
title: Pages
layout: docs
---
# Pages

1.  Add tractor.rb initializer

````ruby
Rails.application.config.to_prepare do
  # Ensure "Pages" is only added once
  unless Tractor::Engine.config.sidebar_content_items.any? { |item| item[:name] == "Pages" }
    Tractor::Engine.config.sidebar_content_items << {
      name: "Pages",
      icon: "bi-link-45deg",
      path: "/admin/pages"
    }
  end
end

````
uncommment the active storage variants gem
gem "image_processing", "~> 1.2"

bundle

install 
bin/rails active_storage:install
bin/rails db:migrate

add a public and private storage in storage.yml
ADD .ENV WITH PUBLIC_STORAGE_SERVICE="public" ?!
