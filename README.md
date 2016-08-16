## Push an app and provide us with feedback ##

I quickly signed up for a free account at [https://run.pivotal.io/](https://run.pivotal.io/). 
The sign-up process was incredibly simple. One little item is that the password requirement was 
very weak I use an old six character password with just numbers and digits but as this is a 
trial I guess its no big deal.  

I check to see if I had a copy of cloud foundry floating around on my mac as I am sure that I have 
played with openstack at some point, but maybe not on the computer.  

```
$ cf - version
-bash: cf: command not found
```

Run a quick cloud foundry cli installer based install and viola

```
$ cf - version
cf version 6.21.1+6fd3c9f-2016-08-10

$cf login -a api.run.pivotal.io
API endpoint: api.run.pivotal.io

Email> codemarc@gmail.com
Password> 
Authenticating...
OK
 
Targeted org codemarc-net
 
Targeted space development
               
API endpoint:   https://api.run.pivotal.io (API version: 2.58.0)
User:           codemarc@gmail.com
Org:            codemarc-net
Space:          development
```

---
I used the the basic ruby (kudos Brian Cunnie) to implement 
[hello-world app definition](https://blog.pivotal.io/labs/labs/worlds-smallest-iaas-part-4-hello-world) 
While I was creating the files, I made a little typo in naming config.ru (I named it cnfig.ru) and 
it certainly caused an error/crash. So I looked at the logs :

```
$ cf logs hello-world-pm --recent

Connected, dumping recent logs for app hello-world-pm in org codemarc-net / space development as codemarc@gmail.com...

.
.
.

2016-08-15T20:51:17.00-0400 [APP/0]      ERR configuration /home/vcap/app/config.ru not found
2016-08-15T20:51:17.00-0400 [APP/0]      OUT Exit status 1
2016-08-15T20:51:17.02-0400 [CELL/0]     OUT Exit status 0
2016-08-15T20:51:17.16-0400 [CELL/0]     OUT Destroying container
2016-08-15T20:51:17.17-0400 [API/3]      OUT App instance exited with guid 3ffd2281-83aa-4e2a-b68f-c711a6cc35fb payload: {"instance"=>"", "index"=>0, "reason"=>"CRASHED", "exit_description"=>"2 error(s) occurred:\n\n* 2 error(s) occurred:\n\n* Exited with status 1\n* cancelled\n* cancelled", "crash_count"=>1, "crash_timestamp"=>1471308677030737556, "version"=>"8d3fe6e2-bafc-4437-8671-1781c381d614"}

```

Now that it was all working I made it look a little better by adding some style (update the font and add the pivotal
favicon).


## This was kind of easy
Developing and testing this way is relatively normal for me since I spend a fair amount of time working 
with docker building and packaging applications see my github [The Infrastructure Problem](https://github.com/codemarc/twip). 

