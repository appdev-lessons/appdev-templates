# Our templates in appdev-projects

* Table of Contents
{:toc}

We have a number of template repositories prepared in the `appdev-projects` organization for you to use for your personal projects:

* [appdev-projects/html-template](#html-template){:target="_self"}
* [appdev-projects/ruby-template](#ruby-template){:target="_self"}
* [appdev-projects/sinatra-template](#sinatra-template){:target="_self"}
* [appdev-projects/rails-7-template](#rails-7-template){:target="_self"}

This lesson details each template and how to make use of them.

## Create repository from template

As opposed to the graded class projects, which you will begin by clicking a "Load [assignment]" button and forking, for our template repositories, you will manually create your own blank app. 

The steps are covered in the ["`.github.io` personal site lesson"](https://learn.firstdraft.com/lessons/58#generating-from-a-template), but they apply to all of the project templates in general:

- Once you have signed in to GitHub, visit the template of your choosing (e.g. [appdev-projects/html-template](https://github.com/appdev-projects/html-template) is a good one for hosting static HTML pages) and click the "Use this template" button, and select "Create a new repository" from the dropdown:

<!-- ![](/assets/gh-pages-template-1.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686161492/gh-pages-template-1_tlxhbl.png)
{: .bleed-full }

- On the next screen, leave the "Owner" dropdown alone, it should be set to _your_ GitHub username.
- For "Repository name", enter any name you would like for your new project. **You should choose a unique, memorable name for the repository. It does not have to match the template name.**
- Make sure the "Public" option is selected. 
- Click "Create repository from template".

<!-- ![](/assets/gh-pages-template-2.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686166582/gh-pages-template-2_rvvdb4.png)
{: .bleed-full }

After a moment you will be brought to the new page at `github.com/<your-username>/<name-you-chose>`, with a copy of all the code from that template. You can get to work right away in a new Codespaces workspace. Be patient, it will take about two full minutes to fully prepare, but subsequent boots of the Codespace will be much faster from [your `github.com/codespaces` dashboard](https://github.com/codespaces).

<aside markdown="1">
You can also work on any project on [Gitpod](https://learn.firstdraft.com/lessons/48), or in a [local setup](https://learn.firstdraft.com/lessons/49), but we recommend sticking with Codespaces as your development environment for now.
</aside>

### This is not a fork

**This is not a fork, this is a newly generated codebase from a template repository.**

What does that mean for us practically?

* Just like a fork, the template generated repo contains a snapshot of all of the code in the repository you generated the template from.
* The template generated code is not tied to the upstream forked repository, meaning that changes to the upstream fork (i.e. commits) cannot be easily fetched into the new codebase.
* Creating Codespaces from the template generated repo [will use your free monthly Codespace hours](#a-note-about-codespace-hours){: target="_self"}.
* Template generated code is not graded, so `rake grade` won't be necessary. The templates are just there for you to have fun with and build your own apps!

### A note about Codespace hours

When you generate a repository from a template, rather than forking it in the case of the graded projects, the Codespaces hours that you use will be billed to **your personal account rather than the `appdev-projects` organization**. But fear not, all GitHub accounts have 60 free Codespace hours per month included.

<aside markdown="1">
Technically, all GitHub accounts have 120 free CPU hours (or 180 for Pro accounts) on Codespaces. By default, a new Codespace is generated on a 2-core machine (2 CPUs), hence 120 core hours ➗ 2 cores = 60 hours. You can [increase the number of cores](https://learn.firstdraft.com/lessons/47#increasing-cores-on-a-codespace), but beware of that eating into your free hours significantly.
</aside>

You can also apply for education benefits on [education.github.com](https://education.github.com/discount_requests/application). Just select "Student" and ideally use a `.edu` email address associated with your school. After a processing period, your account will be upgraded to a free GitHub Pro account, which includes 90 free Codespace hours!

Likely, the 60 (or 90) free monthly Codespace hours will be sufficient for you to work on side projects, as the majority of time spent coding will be on graded forks of non-template projects.

If you're ever unsure of who is paying for the Codespace hours in a given repository, just have a look at the note in the "Code" dropdown menu when you create a new Codespace:

<!-- ![](/assets/who-pays-for-codespace.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686181395/who-pays-for-codespace_rtvrwn.png)

## HTML Template

We made use of the HTML Template beginning in the [deploying static "Hello, World" lesson](https://learn.firstdraft.com/lessons/55), which was actually just a project we generated from that template and added a couple of `rake grade` tests to. It's a good template for creating static HTML + CSS sites and deploying to GitHub Pages.

You can find the repository at:

* [appdev-projects/html-template](https://github.com/appdev-projects/html-template)

If you want to deploy a website from this template, just follow the instructions in the "Hello, World" lesson to [enable GitHub Pages](https://learn.firstdraft.com/lessons/55#enable-github-pages-deployment), and [deploy the app](https://learn.firstdraft.com/lessons/55#deploy).

### "Hidden" files

You may have noticed something a bit odd about the `appdev-projects/html-template` repository compared to Codespaces that you made from forks or templates of it.

The repository page on `github.com/appdev-projects/html-template` has a whole bunch of files and folders in it:

<!-- ![](/assets/hidden-files-vscode-1.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686182198/hidden-files-vscode-1_lsrufp.png)

But, when you booted up a Codespace, the integrated VSCode file explorer appeared to be completely empty:

<!-- ![](/assets/hidden-files-vscode-2.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686182995/hidden-files-vscode-2_jsrsjw.png)

I can assure you, the files _are_ there, but early in your developer journey we didn't want to distract you with all the supplementary files needed to do things like setup the Codespaces environment, monitor your Git version controlling, run the live preview with `bin/dev`, and more. So we "hid" them in the VSCode explorer!

Curious? Just go to a terminal and run the command: `ls -a` (`ls` for "list" and `-a` for "all" files and folders in the current directory including any that start with a `.`):

<!-- ![](/assets/hidden-files-vscode-3.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686182996/hidden-files-vscode-3_qr9h7m.png)

But what if you wanted to actually open one of those files to make some changes? You probably don't want to do that in early projects, but if you ever need to, you can simply run the command: `code <file-name>` or `code <folder-name>/<file-name>` and it will open that file in your editor pane.

And, FYI, we hid the files by modifying the `.vscode/settings.json` file like so:

<!-- ![](/assets/hidden-files-vscode-4.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686182997/hidden-files-vscode-4_b0eku7.png)

## Ruby Template

Following our Intro to Ruby lessons, a useful template for spinning up quick Ruby projects can be found here:

* [appdev-projects/ruby-template](https://github.com/appdev-projects/ruby-template)

Similar to the `html-template` we also [hid some of the setup files](#hidden-files){:target="_self"}, to give you a cleaner file explorer when you are starting out.

## Sinatra Template

As we transition from HTML to coding in Ruby, we will slowly build up a dynamic web app beginning from the bare-bones `appdev-projects/ruby-template` with various Ruby files that we iteratively add. Eventually, we will have many files that are wired together using the lightweight [Sinatra](https://sinatrarb.com/intro.html) framework, which is like a lean version of Rails.

If you want to build your own apps using that Sinatra framework, then we have prepared another template repository at:

* [appdev-projects/sinatra-template](https://github.com/appdev-projects/sinatra-template)

In this case, we aren't hiding any files from you in the VSCode explorer window. It's time to get used to seeing a whole lot of files, because this is nothing compared to the Rails infrastructure!

If you want to deploy an app based on the Sinatra template, see the instructions for Fly.io deployment for a [non-database dynamic app](https://learn.firstdraft.com/lessons/62#deploying-a-dynamic-sinatra-app), or a [database-backed CRUD app](https://learn.firstdraft.com/lessons/62#deploying-a-crud-sinatra-app).

## Rails 7 Template

Finally, Rails. When we learn Rails, the number of files to keep track of grows very large, and there are many files that we won't even discuss, but are important for the functioning and security of the app.

You can find a Rails version 7 template repository at:

* [appdev-projects/rails-7-template](https://github.com/appdev-projects/rails-7-template)

If you want to deploy a CRUD Ruby on Rails app, see the instructions for [Fly.io deployment](https://learn.firstdraft.com/lessons/62#deploying-a-crud-rails-app).
