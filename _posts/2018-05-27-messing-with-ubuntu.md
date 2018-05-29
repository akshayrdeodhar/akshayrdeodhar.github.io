---
layout: post
title: "The story of my experiments with Ubuntu UI, Part One"
date: 2018-05-27
---
# The Beginning
My experiments with Ubuntu's UI started a month ago, with my exams hiding round the corner, ready to say 'Boo !' I, as usual was whiling my time away instead of doing something productive. As hax0r wannabes like me know, Linux has a 'shell', which makes it inherantly cooler than Windows. (Jokes aside, you seriously should shift to some Linux distro if you are serious about programming and computers. Don't embarass yourself.) I already *had* Ubuntu.  But the whole *Cool hax0r wearing hoodlie *hacking* away on Matrix-like shell* vibe was missing. That's when I decided to get myself a 'Kool' desktop enviornment. It was time to go Kubuntu !
Kubutu is  a flavor of Ubuntu with a prettier user interface. It is managed by the KDE Community
The [KDE Project](https://www.kde.org/) , I think was the 'Kool Desktop Enviornment' project in the past. But now it no longer means that, as no complany which calls itself 'Kool' is likely to get donations from tech giants like Google or Canonical
I wanted to go Kubuntu, but leaving Ubuntu seemed like a recipe for disaster. (noobies, huh ?). But a solution presented itself. (rather I googled it, trawled stackexchange and found a step by step solution written by an experienced user)
```bash
sudo apt install kubuntu-desktop
```
This will add the KDE Plasma desktop enviornment to Ubuntu.
Now kubuntu-desktop isn't itself the Plasma enviornment. Rather, it's a metapackage which depends upon several packages. These packages together form Plasma.
These are all 'Kool' packages. They boldly advertise this fact in their names. The names of almost all of thesre start with a 'K'. There are a few cool packages (like konsole), radical ones like kde-connect (this one interfaces your PC with your Phone, and allows easy data transfer- copying links using kde-connect is handy, and even lets you use your phone as a touchpad) and shit apps like Kate (go vim !) or Konversation which you will (and must) never use.

After a 1.2GB download, the installer told me to choose a display manager. I prudently chose lightdm (literally 'light desktop manager'). kubuntu-desktop was installed successfully. The post I was referring to told me to restart, and chose Plasma as my UI when I hit the login screen. This I was unable to do, after repeated restarts.

> Madness is doing the same thing again and again, and expecting diffrent results

So in public interest here is what you have to do:
Click *this* icon
![Click THIS unity icon](/images/icon.png)

Chose 'Plasma' (bad things have happened when I chose GNOME. But if you are a true hax0r, you must be demeaning about Unity. (Rightly so. Canonical collects user data, and shamelessly states that it does so)).
![Plasma](/images/plasma.jpeg)

It was at this juncture that I realised that KDE was like windows. For one thing, it took a noticably longer time to load than Ubuntu. It's windows have the [] _ X buttons at the top right, like window's windows. Anyways, it does have  a lot of interesting features.
There is a conscious effort to make stuff user friendly. The problem is, the general definition of user-friendly is windows-like. It is NOT user friendly to an ubuntu user.  But it IS beautiful.

# The Kubutu enviornment
![Kubuntu's Desktop](/images/kubuntu_desktop.png)

Kubuntu Desktop's defining feature is the ability to add and customize widgets. There are a few built-in ones, like the clock or the menu widget.
Widgets. More widgets are also available for download. 

# The Menu Widget
![Menu](/images/menu_widget.png)

Calender	
![Calender](/inages/calender2_widget.png)

Kubuntu has a smooth look and feel. 
But Kubuntu also has a few REAL features.

# Run Command
This is a really nice utility. There are times when you want to run a single command. Kubuntu lets you do this without going through the whole ritual of starting the shell, running the command and closing it.
![Run Command](/images/run_command.png)

# Clipboard
Another nice feature is it's clipboard history. (which can get a little weird at times)
![Clipboard](/images/clipboard.png)

# Conclusion
Kubuntu was a nice experience. But like several other things (like game piracy or making your own mix-in ice-cream) the process was more fun than the result. After about two hours of using Kubuntu I switched back to Ubuntu. I guess it must be because I am not Kool enough. But the brief flinggave me several mementos- like a longer start-up time and spontaneous unexplained 'System Program problem detected' pop-ups (which exort me to report the problem to Canonical rather than telling me what the problem was- something suspiciously similar to windows).

![system problem detected](/images/system-program-problem-detected.png)

But more importantly, it gave me confidence- the confidece that I could play around with the system and emerge with a scratch.
![tisbutascratch](/images/butascratch.jpg)

Armed with this new-found confidence, I had other adventures, one of them with 'plymouth'. But that, belonging to the horror genre, is a tale for another day and hour.

I hope I haven't scared potential readers away already.
Peace, be Kool !


