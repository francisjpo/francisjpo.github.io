---
title: BASH .profile customized
excerpt: BASH .profile customized for users and root.
tags: mac, sysadmin
date: 2009-04-22 21:52
slug: bash-profile-customized-macosx
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: programming
---

A few years ago I even had a smiley :) vs. :(

{% highlight bash %}
$ francis@persephone ~ $ cat .profile
PS1='\[\033[01;31m\]\u@\h \[\033[01;34m\]\W \$ \[\033[00m\]'
if [ "$PS1" ]; then complete -cf sudo; fi
alias ls='ls -G'
alias cp='cp -i'
alias mv='mv -i'
alias rm='rm -i'
homebrew=/usr/local/bin:/usr/local/sbin
rubygems=~/.rbenv/versions/2.0.0-p195/bin
export PATH=$homebrew:$rubygems:$PATH
if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi
export MANPATH="$MANPATH:/usr/local/man"
export env ARCHFLAGS="-arch x86_64"
{% endhighlight %}

{% highlight bash %}
$ francis@persephone ~ $ cat .inputrc
"\e[A": history-search-backward
"\e[B": history-search-forward
set show-all-if-ambiguous on
set completion-ignore-case off
{% endhighlight %}

{% highlight bash %}
$ root@persephone ~ # cat /var/root/.profile
PS1='\[\033[01;33m\]\u@\h \[\033[01;34m\]\W \$ \[\033[00m\]'
if [ "$PS1" ]; then complete -cf sudo; fi
alias ls='ls -G'
alias cp='cp -i'
alias mv='mv -i'
alias rm='rm -i'
if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi
{% endhighlight %}