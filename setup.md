**Prerequisites**

  - [Python3] (https://www.python.org/downloads/release/python-363/) (you dont have to uninstall python2)
  
  
**Getting your discord token.**

  1. Log in to discord.
  2. Access developer tools in browser or in-app.
  3. Go to the applications tab, expand `local storage`, and click on the link.
  4. Find the key called `token` and copy the value. The value *without the quotation marks* is your token.

**Downloading the bot file**

  1. Go to the [raw main file](https://raw.githubusercontent.com/Kyousei/SelfBot/master/SelfBot/main_file.py).
  2. Right click on the page and select `Save As...`. Keep the `.py` extension, rename the rest if you want.

**Editing the main file**

  1. Open the `main_file` in a text editor 
  2. Set your prefix by putting it inside of the quotation marks. It is set as `.` by default.
  2. Put your token inside of the quotation marks.
  3. Replace `HEX-HERE` with the hex code of the color you want your embeds to be. Do not replace `0x`.
  4. Save and close the file.

**Running the bot**

  Double-clicking the `main_file` should work. Otherwise, you can use `python3 path-to-main_file`.
  

**Oh no! It no worky :(**

  ```Bot has no attribute: say``` 

  In command prompt or terminal, run `pip3 uninstall -U discord.py` and then `pip3 install -m discord.py`.
