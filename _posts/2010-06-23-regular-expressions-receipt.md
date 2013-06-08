---
title: Regular expressions (regexp)
excerpt: Regular expressions in a nutshell.
tags: mac, sysadmin
date: 2010-06-23 14:31
slug: regular-expressions-receipt
author: Francisco Pinto
layout: post
location: Málaga, Spain
type: programming
---

- Metacharacters: \ ^ $ . [ ] { } | ( ) * + ?
- . matches any single character (exclude newlines)
- [abc] matches a single character that is contained within the brackets.
- [0-9][a-z][A-Z] matches a single character that is contained within the brackets.
- [^abc] matches a single character that is not contained within the brackets.
- ^ matches the starting position.
- $ matches the ending position.
- ? matches the preceding character zero or one time.
- * matches the preceding character zero or more times.
- + matches the preceding character one or more times.
- abc|123 matches “abc” or “123”.
- ^.*$ matches “abc” or “123”.
