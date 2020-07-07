---
extends: _layouts.post
section: content
title: Getting started with .NET Core
date: 2020-07-07
description: Let's finally do .NET Core
featured: true
cover_image: /assets/img/posts/getting-started-with-dot-net-core/asp-net-core.png
categories: [.net, .net core, c#, asp.net, asp.net core]
---

I've got some nice idea for my side project (uh, another one) and this time I wanted to do something besides Laravel. So I decided to try .NET Core or ASP.NET Core. It's not really my first time - I have been practicing .NET Core back when it was in Alpha and Beta stages - to be honest, I was really excited about the idea of running .NET on Linux devices and I believed this would be an end of PHP. I was so wrong. 

Anyways, in this mini series I will go through .NET Core and TDD - as I do my Laravel projects. It's possible that there will be some specifics that are more common in Laravel world - simply because I am part of Laravel world. So please, don't get mad at me for doing it "the PHP way".

## Installing .NET Core

This part is simple - simply visit the (.NET Core Page)[https://dotnet.microsoft.com/download/dotnet-core/3.1], download the installer for your operating system and run it. After the installation is complete, you should have `dotnet` command line utility available in your prefered terminal. The current LTS version is 3.1.

And what about IDE? Well, the best way is to use Visual Studio, which ofcourse is only for Windows (I can hear some folks screaming about how there is a version for macOS too - but trust me, it's not even close), however I want to have a cross-platform project and Visual Studio is just not gonna cut it. Visual Studio Code it is! But you can use anything else too.

## Creating our project

So, if you have never been in .NET world before, Solution is a term that is used to represent your whole project. Single solution can contain multiple projects - and that's how we usually structure .NET application. To start, we have to create a solution (.sln) file which will connect multiple projects.

First step first: create a new project folder and cd into it.

Then run

`dotnet new sln`

This will create a new .sln file with a name of current directory. Then, we want to create a project and add it to that file. We can run a `dotnet new` command to see all the available templates.

![New project templates](/assets/img/posts/getting-started-with-dot-net-core/dot-net-core-new-project-templates.jpg)

We want to build Web Api so we will choose that template. Let's create new project and use that template.

```bash
dotnet new webapi -n MyProject.Api
```

We want to name our project "MyProject.Api" so we specified the name using -n flag. You can of course name it anything you like.

We also want to add the newly created project to our solution and we can do that using the following command.

```sh
dotnet sln .\MyProject.sln add .\MyProject.Api\
```

The project is created and we can open the solution with our editor.

```
code .
```

## Running the api

After opening the project with Visual Studio Code, it will immediatly detect that you have a C# project - and it will ask you to install C# extension. Do that as it will make your life much better. 

### Running the project with VS:Code

If your IDE (or editor) is Visual Studio Code and you installed the C# extension than running the project is simple: press F5. The new dialog should pop-up which should let you choose the environment you want to run - you should see .NET Core and pick this one.

![Selecting the debugging environment](/assets/img/posts/getting-started-with-dot-net-core/dot-net-core-debuging-environments.jpg)

The default browser should open after few seconds and you should see 404 page - damn. Nothing to worry about - if you check the controller, you should see that you want to navigate to `/weatherforecast` to see some data.

![Web Api demo project](/assets/img/posts/getting-started-with-dot-net-core/dot-net-core-default-project-demo-data.jpg)

### Running the project without VS:Code using terminal

Of course one may not like the VS:Code and wants to run the project anyways. In that case, we can use the old good terminal. Simply use the `dotnet build` and `dotnet run` to achieve the same results as before. You will have to specify the project you want to run using the `--project` flag, like so:

```
dotnet run --project .\MyProject.Api\
```

## Adding the solution to GIT repository

Our first project is created and we want to add it to the GIT. Let's initalize git repository with `git init`. If you run `git status` now, you will see that there are also some .dll's, .exe's and other files in our git repo, which we don't want - atleast not on git. So, create a new .gitignore file in the root of our solution and add the following code to it.

```
*.swp
*.*~
project.lock.json
.DS_Store
*.pyc
nupkg/

# Visual Studio Code
.vscode

# Rider
.idea

# User-specific files
*.suo
*.user
*.userosscache
*.sln.docstates

# Build results
[Dd]ebug/
[Dd]ebugPublic/
[Rr]elease/
[Rr]eleases/
x64/
x86/
build/
bld/
[Bb]in/
[Oo]bj/
[Oo]ut/
msbuild.log
msbuild.err
msbuild.wrn

# Visual Studio 2015
.vs/
```

I got it from here: https://github.com/dotnet/core/blob/master/.gitignore.

After that, just commit and push the project to the remote.

### Next steps

In the next part we will add test project which we will use to test all of our features - using the TDD way.

See ya!
