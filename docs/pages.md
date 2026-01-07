---
title: Pages
layout: docs
---
# Pages

Houston has a built in pages capability.  Let's enable it and create some pages. 

## Add config/initializers/houston_cms.rb initializer

````ruby
Rails.application.config.to_prepare do
  # Ensure "Pages" is only added once
  unless HoustonCms::Engine.config.sidebar_content_items.any? { |item| item[:name] == "Pages" }
    HoustonCms::Engine.config.sidebar_content_items << {
      name: "Pages",
      icon: "bi-link-45deg",
      path: "/admin/pages"
    }
  end
end
````

## add routes for pages

 ````ruby 
 resources :pages, only: [ :index, :show ]
 ````
## Using Pages
Restart the dev server and follow the sidebar links to create a page. The Slug field will auto-generate from the title, or you can override it here. 

![Create Page](/assets/images/create-page.webp)



Once you have created the page, an extra area will be available allowing you to compose the page using flexible content fields.  Houston comes with two built in. 

### Editor Section 
The Editor section adds a simple Markdown Editor field.  You can assign templates, which you can override.  


### Show the Page

Make a controller to show the page

````ruby
class PagesController < ApplicationController
  add_breadcrumb "Home", :root_path

  def show
    @page = Page.friendly.where(published: true).find(params[:id])
    add_breadcrumb @page.title
  end
end
````


Create a show template to display your page
````erb
<%
provide(:title, "#{ @page.title}")
provide(:description, @page.description)
provide(:canonical, page_url(@page.slug))
%>

<% if @page.banner.attached? %>  
    <div class="banner">    
      <%= image_tag @page.banner.variant(:full), alt: @page.title, class: "" %>
      <% if @page.banner_text.present? %>
        <div class="prose banner-text">
          <%= md @page.banner_text %>
        </div>
      <% end  %>
    </div>      
<% end %>

<%= render 'shared/breadcrumbs' %>

<div class="narrow-content pt-4">
  <%= render "#{@page.template}", page: @page %>   
</div>
````



Add the templates you need.

````erb
/views/pages/_default.html.erb
 <% if page.show_title %>
  <div class="container">
        <h1 class="mt-4"><%= page.title %></h1>
  </div>  
 <% end %>
 <%= render "pages/sections", page: page %>  
````

````erb
/views/pages/_sections_.html.erb
<% page.sections.order(position: :asc).each do |section| %> 
    <div class="section-<%= section.template %>">
      <%= render "/shared/sections/#{section.sectiontypeable_type}/show", section: section %>  
    </div>  
<% end %>
````

And thats it! You can view your pages.  Notice how easy it is to change the page show template to match your site design.  Houston is giving your powers without restrictions.  

