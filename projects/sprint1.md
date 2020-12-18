---
title: Sprint 1 Project
layout: page
---

# StudyScape

Let StudyScape manage your school life easily, all in one place! Nowadays, there are too many individual tools to manage certain aspects of student life: multiple planner apps to manage your tasks, multiple online calendars, such as Google Calendar, to track your schedule, and so many more. We've eliminated the multitude of versions of the same concept and combined them in one nifty application: StudyScape!

## Setup
1. Create or sign in to your Github account.
2. Fork this [repository](https://github.com/MLH-Fellowship/Student-Planner)
3. Clone your fork of the repository and define an upstream remote pointing back to the Connectify repository that you forked in the first place.
```
git clone https://github.com/MLH-Fellowship/StudyScape.git 
cd StudyScape
git remote add upstream https://github.com/MLH-Fellowship/StudyScape.git
```
4. Start the server by running
```
python -m http.server
```
5. Open http://localhost:8000 in your preferred browser. 

## About the Project
Our dashboard is configured with Google sign-in, so you can use your Gmail account to sign in to our customizable dashboard. Here, you can drag and drop widgets into your dashboard to tailor it best to how you work! Our widgets include features such as:
 - Google Calendar, which can display your classes and events
 - To-do list, which lets you create multiple task lists. 

## Technologies Used:
 - HTML/CSS
 - Bootstrap
 - Javascript
 
 ## Inspiration

For this project, we wanted to create an application where students could organize what they needed for studying (notes, schedules, and to-do lists) in one place. As students ourselves, we realized that it's difficult to stay organized across a variety of different platforms, so we wanted to create a centralized hub where students could access everything they needed. Additionally, we wanted to create an interface that's user-customizable, since we realized that everyone learns differently.

## What it does

The user can log into StudyScape using their gmail account from the homepage. From there, they are redirected to the dashboard, where the user can drag and drop widgets (for right now there is a calendar and a to-do list), into different sections of the board. The calendar widget displays the 10 upcoming events on their Google calendar, while the to-do list allows the user to add, check off, and delete tasks from a list.

## How we built it

The user interface was created with HTML/CSS with Bootstrap and Javascript. We used the Google Calendar API for the calendar widget and the Google's OAuth for the sign-in compatibility.

## Challenges we ran into

We originally had a backend that used Node.js and Express, but eventually we had to get rid of it. We also had to redo the to-do list widget due to an error.

## Accomplishments that we're proud of

We're proud of creating a working start to the project we envisioned at the beginning of the sprint.

## What we learned

We learned a variety of new tools and technologies that we hadn't worked with previously. Also, we learned a lot from focusing on using Github effectively and from having to communicate across time zones.

## What's next for StudyScape

We are hoping to implement the notes widget into the dashboard, along with other tools (such as a pomodoro timer) to augment the quality of the user experience.

## Contributors
 - [Emily Amspoker](https://github.com/eamspoker)
 - [Vividha](https://github.com/V2dha)
 - [Shilpita Biswas](https://github.com/sh-biswas)
 
 ## Demo
https://www.youtube.com/watch?v=RHA8MtWvvEQ&feature=youtu.be
