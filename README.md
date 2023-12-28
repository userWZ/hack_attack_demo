This project can make the xss attack, csrf attack, sql inject attack.

The main reference is , <a href="https://whitehatways.com/cross-site-scripting-and-cookies-a-delicious-disaster/">linked here</a>, first download this project to your local computer. 

1. Install requirements with
<code>python3 -m pip install -r requirements.txt</code>

2. Run the following commands to get Django up and going!
<br><code>python ./manage.py makemigrations</code>
<br><code>python ./manage.py migrate</code>
<br><code>python ./manage.py createsuperuser</code>
<br>&emsp; Following the prompts here!
<br><code>python seed.py</code>

3. Run the server
<br>Run <code>python ./manage.py runserver</code> to begin!

4. To XSS
The post page can add comment and show the comments written by logged or anonymous users. So the anonymous users can 
inject the script code in the comments by XSS. Everyone open the post page will trigger the xss code which may leak
users information such like cookies, passwords and affect the use of the website.

some xss code like:
- steal cookies from logged-in users
<code><script>alert(document.cookie.split('; ')[1]);</script></code>
- alert something to interference 
<code><script>alert('You've been hacked');</script></code>
- Listen to the user's keyboard input
<code><script>document.addEventListener('keypress', function (event) {console.log(event.key)})</script></code>

5. To CSRF
To CSRF We need to open a fake website by http server use following bash code
<code>python -m http.server 8080</code>


6. To sql injection
The home page have a search input which have risks of SQL injection,
We can inject the database by some SQL code such like:
- get django user list
<code>z' UNION SELECT first_name FROM auth_user WHERE first_name LIKE '</code>
- get the email of django user 
<code>z' UNION SELECT mail FROM auth_user WHERE first_name LIKE '</code>

  
Happy Hacking! :)