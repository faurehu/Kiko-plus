---
layout: post
title:  "strategies for software development on the iPad"
description: "or how to survive without a computer"
date: 2018-10-30 16:57:08 +0100
category: english
epistemic_status: ""
epistemic_effort: ""
last_modified_at: ""
---

Apple has released a new iPad Pro intended to replace a traditional computer, at least for most users. This means that an iPad is now should now be fully equipped to support your spreadsheet activities and photo editing endeavours, which will be enough for most. Apart from video editing or hosting services, there remains a task that escapes the iPad's realm: software developing.

Apart from sandboxed IDEs, there is no freedom to create your own runtimes that have command of kernel APIs. However, this does not mean that you cannot develop on your iPad. Here are a few strategies I myself have tried:

## Tmux mirroring

On my main driver, I run an Arch Linux install with i3 as a Window Manager. On pressing space + return, I can spawn terminals. Each spawned terminal window is automatically a new tmux session.

![png]({{site.url}}/assets/images/terminal-based-computing/arch.png)

My main driver is also always running a SSH daemon, which allows remote terminals to connect to my desktop. iOS has many SSH client apps, but none is better than [Blink](http://www.blink.sh/). It has great features such as mosh protocol support, which will allow you to keep your SSH connection even as you leave the app while using other applications. It also has support for running commands as soon as you SSH into your target host, allowing me to automatically create a tmux session.

Because everything is hosted on tmux, I can access everything that is also being displayed in my desktop. Say I was editing something on VIM and had to leave, I'm be able to pick up my work where I left, right from my iPad!

![jpg]({{site.url}}/assets/images/terminal-based-computing/tmux.jpg)

## Jupyter hosting

I do a lot of work on jupyter, and even draft blog posts on this editor. Jupyter is web based so you can easily open your port and access the editor from any web browser on your iPad. For security reasons, you are going to need distributing X.509 certificates to your client devices so that your connection is secure.

## React development

Achieving comfortable front-end development is still tricky. You can host your development server and allow remote connections to it, so that you can test your changes on your iPad browser while you edit the files on your SSH client. This is also possible with React Native, considering that [Expo](https://expo.io/) will allow you to push your development versions to a cloud repository which will automatically be pushed to your native iPad app.

The main limitation to this is that there are no developer tools on iPad web browsers.

