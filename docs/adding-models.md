---
title: Adding Models
layout: docs
---
# Adding Models


To generate an admin section for an existing model, you can run the generator:

````
  rails g scaffold_controller Admin/Boat name:string description:text length:integer    --model-name="Boat"
````

override app/views/admin/shared/sidebar/_app_specific.html.erb to add admin areas for app specific items

````ruby
<ul class="admin-sidebar-menu" >
  <li class="">
    <a href="/admin/boats" class="">
      <i class="bi bi-link-45deg"></i>
      <span class="">Boats</span>
    </a>
  </li> 
</ul>
````