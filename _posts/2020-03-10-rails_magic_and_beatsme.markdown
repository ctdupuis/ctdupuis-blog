---
layout: post
title:      "Rails Magic & BeatsME"
date:       2020-03-11 01:55:35 +0000
permalink:  rails_magic_and_beatsme
---


Wow. Rails sure is magical. The entire Rails section of the curriculum took everything that was taught in Sinatra and made it "magical".
By "magical", I simply mean it took a lot of the coding we did and added short-hand helper methods that made everything more abstract and clean. Instead of defining all of our routes and mounting controllers, now that can be done in one line. Thanks to Rails, I can simply generate a model and full CRUD functionality through one single line of code. I didn't use that feature (scaffold generator) partially because we weren't allowed to, but mainly because it generates A LOT of code, most of which I'm not terribly familiar with. I would assume anyone who uses a scaffold generator is very familiar with the code it generates and how to use it.

But that's only part of the point.

The main point I would like to address is that Rails offers a very powerful framework to allow developers to quickly build large-scale apps. A famous quote that applies to this is:

  "With great power comes great responsibilty"  -Benjamin Parker, almost every Spider-Man form of media that exists.
	
Just like the scaffold generator, a developer can't really harness this power that Rails offers until they fully understand how it all works. Generators in general are incredibly helpful when it comes to doing work for you. I used many model and controller generators throughout the process, simply because it saved me time by making my files for me in a pipeline that Rails will automatically know how to follow. I only used the amount of power I could handle.

This project was as fun as it was frustrating. By that, I mean when something in my code broke, more often than not, it was very frustrating to locate the exact problem. Rails doesn't always do a great job of helping you debug, so much so that someone even made a gem for Rails (Better Errors) that would display errors in detail for you. The same way that someone made the Corneal gem for building the skeleton of an entire Sinatra app, someone made a gem just for Rails ERRORS. If that doesn't show the size of Rails compared to Sinatra, I don't know what will. Regardless, once I was able to debug properly and actually get my code to function properly, it was one of the most satisfying feelings I've ever experienced. I'll elaborate more on that later.

The app I decided to make for Rails is a music-sharing app called BeatsME. It's mainly a severely watered down version of SoundCloud, where users make an account and have the ability to create albums to share with other users. There's no playback functionality (yet) partially because I have no rights to any of the music that would be shared, but also because I'm not the slightest bit musically talented enough to make my own beats to submit. So for now, BeatsME simply contains info about music, not the actual mp3 files themselves.

Getting into the process, I started where I would imagine most people would: models and model relationships. I wanted users to have functionality to add individual songs but mainly in the context of creating an album. The reason behind this is simply because in retrospect, songs exist inside of an album. Even singles technically belong to an album titled after the song with "- Single" tacked on the end of it. BeatsME allows for the creation of singles, as well as full-scale music albums. Albums is the join table for artists, songs, and genres, and also belongs to a user. An artist will have many songs, but only in the context of the albums that they've created. I limited genres to a selection from my seed file that I took from Google, simply to make it more realistic in forms of forcing users to pick a genre (there are a lot to choose from) instead of creating a new genre that might not realistically make sense. I don't mean to put a definition on art, but it makes the user experience better in my opinion.

The biggest issue I had with designing the app was nesting resources and generating forms for those resources. It got to the point where it was so complex, it made it was benficial for me to design a helper method that helps `form_for` decide which url path to follow. Because I used `form_for` for nested resources, it couldn't simply read a top level resource path, so I had to define a method for identifying the path to submit to. Once that was fixed, I moved to CSS.

CSS took a solid day and a half worth of developing, and I still see many changes I want to make. I spent countless hours learning how to nest `div` tags and how to style them accordingly. Once I started to get the hang of the process, it was smooth sailing and watching the CSS styling in action was very rewarding. Everything was going great until I reached the Playlist feature. 

Expanding upon the playlist feature, users are allowed to make new playlists and add songs of their choice from the entire collection of songs on the app. The CRUD functionality of playlists, however, only exists in the context of a user. Similar to how only verified users can submit new albums, playlists are only constructed through a user's home page. Constructing this nested resource was considerably more difficult, but thanks to doing the nested songs resource beforehand, I was rather familiar with the process and was able to fully add an entire feature in a few hours. 

BeatsME is far from finished. It's a great prototype and meets the Rails project requirements, but I have full intentions of saving this source code for future use. This is the largest scale app I've built so far, and the grueling process has made the current product that much more rewarding. I've never felt so satisfied about seeing hard work pay off, and I'll never forget the trials and tribulations of building BeatsME.
