### Credintials from <a href="http://127.0.0.1:8000/admin/">admin</a> page: 

|  		   |		 |
|----------|---------|
| user:    | admin   | 
| password:| Asdfgh1!|

<p> But it is for my "db.sqlite3" DB. You need to create your own DB and add SuperUser. </p>

**Create yor DB**

<p>Run the following command:</p>
<pre>
$ python manage.py makemigrations polls
$ python manage.py sqlmigrate polls 0001
$ python manage.py check 
$ python manage.py migrate
</pre>

*For more detail search info*

**Creating an admin user**

<p>Run the following command:</p>
<pre>
$ python manage.py createsuperuser

Username: admin
Email address: admin@example.com
Password: **********
Password (again): *********
Superuser created successfully.
</pre>