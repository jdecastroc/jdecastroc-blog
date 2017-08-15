---
layout: post
title: InfoJapon v2, The conception
description: Moving forward a big project with RoR! InfoJapon v2.
published: true
comments: true
category: Dev
tags: [webdev, Ruby, Ruby on Rails, Agile]
---

<p align="center">
  <img src="http://infojapon.com/img/logoBig.png" alt="InfoJapon v1" />
</p>

## What's InfoJapon?
InfoJapon is an application that uses intelligent agents in order to gather relevant information from web pages related to Japan for transform the data and make it visible through a website and an android application accomplishing the user expectations. The user will be able to be informed about the latest articles of the Spanish-speaking blogs related to Japan and also will have access to different modules that allow to make advanced searches about study, work and live in Japan.

InfoJapon born with the objective of become a platform where to connect the user with the updated information about daily topics about Japan through an easy interface making use of the latest technologies. The project expects to centralize the information and grow with the user demand.



At the begining the idea was centralized only the articles written in spanish about Japan but I wanted to do a deep research about web crawlers and how them worked. I was able to use lot of useful tools like ElasticSearch, Pentaho and even RapidMiner in order to get articles from the spanish blogs and list them all in infojapon. Then by using tools like JSoup I learned how to extract information from webpages and clean it. It was a project I am proud of but due to the time limit I needed to follow there were a thousand of features I couldn't implement and the code at the end became a mess due to it was the first time I faced such a project. At that time I didn't know about Agile nor TDD. There are many things I have been learning since the first deploy of infoJapon.

All the code can be found in [the github repository of infojapon](https://github.com/jdecastroc/punto-japon)

## InfoJapon v2
As I am now into ruby and RoR I wanted to introduce those features and redo from zero all the code with RoR instead of Spring in order to practise and gain experience with the framework. Thanks to the feedback of the infojapon users I got what where the most interesting features:
 - Study in Japan (Japanese languages Schools)
 - Articles from the spanish written blogs

Although there are options such search a job and a house in Japan I think is clear that the interest is about study in Japan and the easiest way is to come here and get a student visa for study japanese. That's why I'm going to improve that feature.

The features I couldn't introduce in the project where the following:
- Creation of a module to index and visualize vBlogs
- Creation an improved solution for the blog's crawling
- Creation of a module to manage multi-region encounters via meetup API (Discarded)

Thinking about the feedback and the new features I got to the conclusion that change the actual project into a more social-focused one was awesome. It is an idea that I really enjoy and perfect to continue in my RoR and ruby learning. But how could I mix the old and new features into a new webapp focused on people?. Doing some brainstorming and asking potential users I got the following features:
- Main page listing resources
- Resources could be whatever: articles, videos, podcasts, shared files, links...
- Independent module focused on crawl spanish-written blogs and youtube channels to show in the main page
- Tag and category oriented app
- Social oriented (users, like's system, follows, discussions...)

## The idea behind this post and the start
As I continue learning by doing, getting things done wrong, refactoring, adding new knowledge... I want to document my steps in a series of posts in order to try to track all the proccess. 
First I want to set up my own project management environment with trello.
As I want to apply some concepts I'm learning about [Agile development with Rails](https://courses.edx.org/courses/course-v1:BerkeleyX+CS169.1x+1T2017SP/course/), I started creating a [trello](www.trello.com) panel and creating the following lists:
- List with the product backlog
- List with the spring backlog
- List with the current spring
- List with In Progress
- List with To do 

Then in order to track the different tasks I'm going to divide the tags into the following
- ![#98FB98](https://placehold.it/15/98FB98/000000?text=+) `User story`
- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `Bug`
- ![#1589F0](https://placehold.it/15/1589F0/000000?text=+) `Improvement`
- ![#FFA500](https://placehold.it/15/FFA500/000000?text=+) `Issue`
- ![#BA55D3](https://placehold.it/15/BA55D3/000000?text=+) `Task`
- ![#FFFF00](https://placehold.it/15/FFFF00/000000?text=+) `New feature`

Once the project management environment is finished, is time to start writting some user stories. First let's focus on what the main page is going to list and how. All of them are resources but some of them are going to be automatically added to the database by the web crawlers. For the next post I'm going to start then with the RoR project set up, some logic diagram and the crawlers logic, what to parse and how to automatize it. 

If you have any suggestion to include in the application let me know! :)
