---
layout: post
title: "commit part of a file with Git"
date: 2015-09-12
categories:
---

```
 git add -p file.txt
```

This command will show a list of changes in the file and show some options.

Exemple where I removed the gem bootstrap-sass and added the gem spring

```
$ git diff Gemfile
diff --git a/Gemfile b/Gemfile
index 80641f6..11ec461 100644
--- a/Gemfile
+++ b/Gemfile
@@ -7,7 +7,6 @@ gem 'rails', '4.2.3'
  gem 'pg', '0.18.2'
  
  # Asset Pipeline
-gem 'bootstrap-sass'
  gem 'bootstrap-slider-rails'
  gem 'coffee-rails'
  gem 'font-awesome-rails'
@@ -50,6 +49,7 @@ group :development, :test do
    gem 'mocha'
    gem 'quiet_assets'
    gem 'simplecov'
+  gem 'spring'
  end
  
  group :staging, :production do
```
Using git add -p Gemfile will show this:

```
$ git add -p Gemfile
diff --git a/Gemfile b/Gemfile
index 80641f6..11ec461 100644
--- a/Gemfile
+++ b/Gemfile
@@ -7,7 +7,6 @@ gem 'rails', '4.2.3'
  gem 'pg', '0.18.2'
  
  # Asset Pipeline
-gem 'bootstrap-sass'
  gem 'bootstrap-slider-rails'
  gem 'coffee-rails'
  gem 'font-awesome-rails'
Stage this hunk [y,n,q,a,d,/,j,J,g,e,?]?
```
      
It is showing the first change in the file and the options: [y,n,q,a,d,/,j,J,g,e,?]

Pressing **y** will add only that block and will keep showing the next blocks.