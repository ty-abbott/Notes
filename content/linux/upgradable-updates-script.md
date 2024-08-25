## Creating the script to alert me with updatable upgrades

- using apt list --upgradable to tell me what updates there are
- writing to a text file the output if there are updates that are returned 
- implement a bot account for emails with gmail
- add bot details as persistent environment variables through editing ~/.bashrc and then reloading through source ~/.bashrc
- test with echo $variable
- write python code (this was a big help - https://mailtrap.io/blog/python-send-email-gmail/#:~:text=To%20send%20an%20email%20with,Transfer%20Protocol%20(SMTP)%20server.)
- make sure that the env variables are accessed correctly and that the auth token is used rather than the password!
- I was getting errors when running - AttributeError: 'NoneType' object has no attribute 'encode'
  - this was because I wasnt actually accessing the env variables correctly
- access like this https://developer.vonage.com/en/blog/python-environment-variables-a-primer
