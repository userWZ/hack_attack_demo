This project can make the xss attack, csrf attack, sql inject attack.

The main reference is , <a href="https://whitehatways.com/cross-site-scripting-and-cookies-a-delicious-disaster/">linked here</a>, first download this project to your local computer. 

1). Install requirements with
<code>python3 -m pip install -r requirements.txt</code>

2). Run the following commands to get Django up and going!
<br><code>python ./manage.py makemigrations</code>
<br><code>python ./manage.py migrate</code>
<br><code>python ./manage.py createsuperuser</code>
<br>&emsp; Following the prompts here!
<br><code>python seed.py</code>

3) Run the server
<br>Run <code>python ./manage.py runserver</code> to begin!

Happy Hacking! :)