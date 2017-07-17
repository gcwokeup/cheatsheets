##**Killing all Ruby Processes**
Tue, Sep 24, 2013

I was running some commands that I later found out had left me with many orphaned ruby processes. Too many to kill one by one. I needed to just get rid of them all and quickly so killing all ruby processes was the best way to go.
Here is a short list of convenient and inconvenient ways to do that:  

  for each in `ps -eo pid,command | grep ruby | grep -v grep | awk '{print $1}' `; do kill -9 $each;done  
  killall −9 ruby  
  pkill -9 ruby  
  pidof ruby | xargs kill -9  
  ps aux | grep sidekiq | awk '{print $2}' | xargs kill  


Taken From: [{ always: 'coding' }](http://alwayscoding.ca/momentos/2013/09/24/killing-all-ruby-processes/)  
