---
title: Adding Models
layout: docs
---
# Adding Models
Houston will generate admin views for your models.  they look nice and are 100% editable.  

![boats](/assets/images/boats.webp)

To generate an admin section for an existing model, you can run the task:

````bash
bin/rails "houston:admin:controller[Boat]" 
````
From here, you can edit the form and controller as you need.  

Alternativly,  if you want to specify exactly which fields or their order run the generator directly:

````bash
bin/rails generate houston_cms:admin_scaffold_controller boat name:string description:text --model-name="Boat"
````


To link to your fancy new admin,  override app/views/admin/shared/sidebar/_app_specific.html.erb to add admin areas for app specific items

````ruby
<!-- app/views/admin/shared/sidebar/_app_specific.html.erb -->
<ul class="admin-sidebar-menu" >
  <li class="">
    <a href="/admin/boats" class="">
      <i class="bi bi-link-45deg"></i>
      <span class="">Boats</span>
    </a>
  </li> 
</ul>
````

You can choose any icon from the bootstrap icons set.  or of course customise this HTML to show whatever you want.  it's just HTML and CSS. 

