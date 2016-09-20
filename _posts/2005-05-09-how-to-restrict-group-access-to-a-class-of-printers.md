---
title: How To Restrict Group Access To A Class Of Printers
layout: post
permalink: /blog/:year-:month-:day-:title.html
---

Two ways of restricting groups from accessing a class of printers
    /usr/sbin/lpadmin -p class -u allow:all 
    /usr/sbin/lpadmin -p class -u allow:@staff,@students 
    /usr/sbin/lpadmin -p class -u deny:@staff,@students 

 # Deny everyone except for groups staff and students
 <Class my_class>
 ...
 AllowUser @staff
 AllowUser @students
 </Printer>
 
 # Accept everyone except for groups staff and students
 <Class my_class>
 ...
 DenyUser  @staff
 DenyUser  @students
 </Printer>
