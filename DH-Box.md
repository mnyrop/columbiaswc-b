## DH Box Instructions
### for folks who can't get their systems working

- [ ] Go to http://dhbox.org/
- [ ] Sign up for an account for 1 week
- [ ] When you're logged in, click your username in the top right corner and select Apps
- [ ] Near the top, navigate to the 'Command Line' tab
- [ ] Type in your username and hit enter.
- [ ] When prompted, type in your password and hit enter. The cursor will not move when you type.
- [ ] Once you're logged in to the shell, enter the following commands, hitting enter after each one:<br>
      `mkdir Desktop`<br>
      `cd Desktop`<br>
      `wget -P /home/columbiaswc/Desktop/ 'http://swcarpentry.github.io/shell-novice/data/data-shell.zip'`<br>
      `sudo apt-get install unzip` <~ this will ask for your password<br>
      `unzip data-shell.zip -d data-shell`<br>
      `rm data-shell.zip`
      
__Check:__ If you enter the command `ls` you should see `data-shell`
      
__Note:__ enter the command `clear` to clear the text
