---
layout: post
title:  "5 cool tips for efficient use of git"
date:   2016-09-07 13:48:21 +0100
categories: jekyll update
---
<h1>1. Clone repository over SSH</h1>
Something that frequently annoys me is having to write a password everytime I push content to a git repository on Github. Cloning repositories over SSH is a great way to avoid the extra work of writing your username and password. All you have to do when cloning is to use  
{% highlight bash %}
$ git clone git@github.com:username/example_repository.git
{% endhighlight %}
instead of 
{% highlight bash %}
$ git clone https://github.com/username/example_repository.git
{% endhighlight %}
However if this is your first time cloning over the the SSH protocol on your computer, you might end up with a message like this one.

{% highlight bash %}
Permission denied (publickey).
fatal: Could not read from remote repository.
{% endhighlight %}

This is because identification of your computer is excpected with an SSH key. Generate one with:

{% highlight bash %}
$ ssh-keygen -t rsa -b 4096 -C "you@example.com"
{% endhighlight %}

Then add it to the ssh-agent with: 

{% highlight bash %}
$ ssh-add ~/.ssh/id_rsa
{% endhighlight %}

Enter your Github profile. Go to "settings"->"SSH and GPG keys". Click "New SSH key". Give the new key a descriptive name for your computer and paste the content of ~/.ssh/id_rsa.pub in the "Key" field. Press "Add SSH key". 
Now, you will be able to clone that repository of yours. 

<h1>2. Enable git bash completion</h1>
I love bash completion! Just write a part of your command and HAMMER that TAB key. Just transfer the completion script to a file. 

{% highlight bash %}
curl http://git.io/vfhol > ~/.git-completion.bash
{% endhighlight %}

then add the following line to your bashrc

{% highlight bash %}
# ~/.bashrc
[ -f ~/.git-completion.bash ] && . ~/.git-completion.bash'
{% endhighlight %}

Now, try doing a commit writing only 'com' 
{% highlight bash %}
$ git com
{% endhighlight %}
And SMASH that tab key. You just saved yourself three key strokes.

<h1>3. modified or unmodified in command prompt</h1>






