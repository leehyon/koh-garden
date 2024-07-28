---
title: Setup Web Development
draft: false
tags:
  - javascript
  - setup
---

This is a guide for configuring your local machine for general web development.

## Prerequisites

The key differences between **React** and **Node.js** are:

- React is a front-end JavaScript library for building user interfaces and UI components. Node.js is a back-end JavaScript runtime environment for building server-side applications.
- React deals with what users see and interact with directly in the browser. Node.js deals with server-side logic and operations that occur behind the scenes.
- React renders UI components and manages component state and lifecycle. Node.js executes application code, handles HTTP requests, interacts with databases, etc.
- React code is run in the browser and manipulates the DOM. Node.js code is run on the server/backend and never touches the DOM.
- React handles view layer only. Node.js can handle everything on the server-side like business logic, data access, routing, APIs, etc.
- React is used for building single page applications or SPAs. Node.js is used for traditional web applications with multiple pages.
- React is declarative - you tell it what you want done. Node.js is imperative - you specify exactly how to do it.
- React follows a component based architecture. Node.js follows a module based architecture.
- React is focused on high performance UI. Node.js is focused on high performance networking and application logic.

In summary, ==React handles UI== while ==Node.js handles server-side logic==. They complement each other well in full-stack JavaScript web development.

## Scope

Essentially, there are two different philosophies that define your setup as a web developer. While there are developers who prefer to have all their tooling in one Integrated Development Environment (IDE), there are developers who prefer to use multiple lightweight tools (e.g. editor/IDE, standalone terminal) and combine them for their purposes.

Install the following tools:

- Node.js and npm: to execute JavaScript code and install JavaScript libraries
- VS Code: editor to write code, integrated terminal to execute code

## General steps

1. Choose an operating system: Linux, Windows or MacOS all work well
2. Install a code editor: VS Code
3. Set up a web server stack: Install Apache, Nginx or IIS
4. Learn Git for version control
5. Pick frontend frameworks: React, Angular, Vue.js are popular choices
6. Database systems: Install MySQL, MongoDB or alternatives you need for your projects
7. Debugging tools: Browser DevTools, console logs and debuggers help fix issues in code
8. Project templates: Use boilerplates, starters and templates to quick start projects and standardize structure
9. Build and deployment tools: Webpack, Grunt, Gulp automate optimization and deployment

## Node.js

Here are some tips on how to incorporate Node.js into your web development setup:

- Install Node.js on your machine if you haven't already. 
- Make sure you have a code editor that supports Node.js development out of the box, like VS Code or Atom.
- Learn the basics of Node.js - how to run JavaScript code outside the browser, the module system, asynchronous programming, npm for package management, etc.
- Optionally install a Node.js framework like Express or Fastify if you plan to build web applications. They make creating web servers and APIs easier.
- For the backend or server side of your web projects, use Node.js instead of something like PHP or Ruby. Design your server architecture with Node.js handling HTTP requests, routing, talking to databases, etc.
- Use npm to install useful Node.js libraries and tools for tasks like authentication, database access, performance monitoring, etc. Avoid reinventing the wheel.
- Use Node.js for build tools and automations tasks with build tools like Gulp, Grunt or Webpack. These can be configured via npm.
- Deploy Node.js apps to hosting platforms like Heroku, AWS, Azure etc. Many provide quick onboarding for Node.js apps.

## Learn more

- [Web Development Setup for Beginners](https://www.robinwieruch.de/developer-setup/)
- [How to setup React.js on Windows](https://www.robinwieruch.de/react-js-windows-setup/)
