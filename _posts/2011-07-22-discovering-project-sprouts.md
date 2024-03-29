---
layout: post
title: Discovering&#58; Project Sprouts
link: http://www.psyked.co.uk/discovering-project-sprouts/
author: psyked_james
description: 
post_id: 1356
created: 2011/07/22 10:49:53
created_gmt: 2011/07/22 09:49:53
comment_status: open
post_name: discovering-project-sprouts
status: publish
post_type: post
---

# Discovering: Project Sprouts

_Project Sprouts (<http://projectsprouts.org/>) is something that I'm just starting to get into, following much encouragement from Mark, and a cool presentation from Simon Bailey (<http://www.newtriks.com/?tag=project-sprouts>)._ ![](http://uploads.psyked.co.uk/2011/07/FF181.jpg)

### What is Project Sprouts?

Sprouts is a relatively new project, focussed on ActionScript and Flex development, and makes a whole lot of the setup of new ActionScript and Flex projects much easier. It’s a springboard for new projects, and it automates both the initial configuration of your development tools and the creation of new template-based classes, projects and unit tests. Essentially, that’s what it does out of the box. But in addition to that, it’s also completely configurable (depending on how deep you want to go into Ruby), it’s headless (in that it has no IDE), and it’s platform independent.

### Why should you be interested?

From a practical point-of-view, setting up new projects is a time-consuming process. Setting up MVC frameworks, like RobotLegs or PureMVC, are more of a time sink, and setting up TDD is even more so. Sprouts, on the other hand, sets your projects up based on a template and does it for you – MVC framework and TDD templates included. It’s also then extensible and you can, for example, then integrate tasks like FTP uploads or source-control syncing as part of your build process. 

### How does it work?

It’s all built on Ruby(<http://www.ruby-lang.org/en/>) and uses RubyGems(<http://rubygems.org/>) – that’s all you need. No Flash Builder, no Adobe Creative Suite. Mac and *nix platforms have Ruby built in, I think. Windows PCs have to go download a Ruby installer(<http://rubyinstaller.org/>). 

### Sample code:

When you’ve got it installed, fire up your Ruby Command-Line window and type: 
    
    
    # Install the ActionScript 3 / Flash Bundle:
     gem install flashsdk --pre
    
    
    # Generate a new ActionScript 3 project:
     sprout-as3 SomeProject
    
    
    # Move into the new project:
     cd SomeProject
    
    
    # Install dependencies:
     bundle install
    
    
    # Compile and run the main project:
     rake
    
    
    # Generate a class, test and test suite:
     sprout-class utils.MathUtil
    
    
    # Compile and run the test harness:
     rake test

The initial four lines of code does what otherwise takes hours to achieve. (If you’re doing like-for-like tasks) It downloads the latest Flash SDK, configures it, creates a new project and compiles it. The latter two commands set up unit test templates and runs them. The unit testing templates never really seemed to make sense to me before seeing them used in Sprouts - a lot of setup, if you ask me.  But with the shell classes being auto-generated, it all seems to make sense now!

## Comments

**[Mark Lapasa](#884 "2011-07-22 17:22:34"):** Hey man, this is pretty cool stuff. This looks to be a lot more easier to use than Maven

**[กล้องวงจรปิดลำปาง](#885 "2013-11-29 09:30:47"):** Good way of describing, and nice article to obtain facts about my presentation subject matter, which i am going to convey in academy. Here is my blog ... [กล้องวงจรปิดลำปาง](https://www.facebook.com/cctvlampang)

