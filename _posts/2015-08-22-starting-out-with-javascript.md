---
layout: post
title: "Starting Out With jQuery/Javascript"
date: 2015-08-22 18:55:34
author: Nayyir Jutha
summary: Showcasing basic starter projects for learning the programming language Javascript. 
categories: javascript
thumbnail: javascript
tags:
 - work
 - with
 - javscript
 - jquery
---

#Find the Longest Word

```
function findLongestWord(words) {
    var sortArr = words.sort(function(a,b){
      return b.length - a.length;
    });
    return sortArr[0];
  }

```
With this little function the largest word in an array is returned. Only a few lines of code can do so much, this function clearly exemplifies the power of the Javascript programming language.