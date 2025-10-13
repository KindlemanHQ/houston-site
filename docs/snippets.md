---
title: Snippets
layout: docs
---
# Snippets
Huston comes with snippets as standard because they are just always useful for any site.  Once you start using them you will see their value.  Every little **snippet** of your site becomes editable.  Your PM and client will no longer be asking for little annoying edits. With snippets, they will be empowered and pleased.  

So, login to /admin and click **Snippets** in the side menu. 

Click New Snippet.  
The resulting form is self explanatory.  Give your snippet a name.  Lets try home-title.  Give it some content introducing your lovely website.  You can use markup.  Click save. 


Now, on your website, open the homepage template. 

````ruby
<%= snippet('home-title') %>
````

And tada.  Your content appears. 

When building site's you can also use the utility helper 
````ruby 
<%= snippet_or_create('home-title', "Welcome to the greatest website on planet.", ) %>
```` 
This is very handy for creating default content that will then be deployed to your staging and production servers without having to copy paste all the copy as you move towards go live. 

If you want to add images, click upload files and select them from your computer.  

In the next chapter, we will discover the [media library](/docs/media-library).  