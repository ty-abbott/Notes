# The skinny on geoblocker 

I have decided to change up the scope of this projecct in a fairly signifigant way. No longer will it be a automatic IP blocker(for reasons I post on
the readme and ill post here in the future)but rather a drive by scanning informer(?). Going to gather intel on the IPs that are constantly scanning the internet. 
Why? Because I am curious...

Getting into concurrency with python, essentially I am looking to be able to run different code at the same time {link to concurrency programming notes}
^^Now I have learned that it is actually parallelism, which is different then concurrency
https://github.com/ty-abbott/geoblocker


going to use scapy for network simulation 


Trying to figure out what to do in regards to data base updates and inserts. Do I run these things after every IP is examined? That can be a lot of work. Do I save to state and then do one massive add every so often(then delete state)? 
- For now I think I will just keep it simple and update every time.
- sqlite should have good locking built in for concurrency
