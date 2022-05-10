# Django-Bootstrap Blog and Translator App

There are multiple web frameowkrs available in Python:
1. Django: Easier to work with databases with Django. Django also allows adding more apps within the website.
2. Flask: Building small web applications for emaple translator or converting images to different format, or simpler blogs.
3. JustPy: New framework. Doesn't require html and css knowledge to build a website. This also means its not very flexible. Not good for working with databases. 


<h3><a id="venv">1. Virtual Environment</a></h3>

Virtual environment helps to ensure that only required libraries for the project are installed. 

1. Open terminal and run command: python -m venv env This will create a virtual environment.
2. Select the installed virtual environment (CTRL + SHFT + P, then select "Select Interpreter" and then select the virtual environment just created as defauly python to execute the project).
3. Close the existing terminal and open a new terminal. This time by default the new virtual environment will be used for the project.
4. Insall Django by running command (pip install django). This will only be installed for virtual environment.


<h3><a id="djangoproject">2. Django Project</a></h3>

To work on Django framework there are set of files which are created by Django by default. Here we will carry out the steps for the same.

1. Run command (django-admin startproject mysite .) on terminal. This will create a mysite folder with multiple files. 
<ol>
<li>__init__.py: Optional. Place things that should be executed immediately when the program/app starts.</li>
<li>asgi.py: This config file. Changed to deploy the site on server. Alternative is wsgi.py. One of the them is selected based on the server where it will be deployed.</li>
<li>settings.py: Contains all the settings, the timezone, static files, css files etc.</li>
<li>urls.py: This will have urls of the sites within the projects </li>
<li>wsgi.py: This is config file. Changed to deploy on the server. Alternative is asgi.py. One of the them is selected based on the server where it will be deployed.</li>
</ol>
2. It will also create manage.py file. Run the command (python manage.py runserver). If everything works fine till now, you should have a running webpage.
3. While executing above command, there will be warning (You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions. Run 'python manage.py migrate' to apply them.) As mentioned run the (python manage.py migrate) command in terminal. This will create some default tables for you. You will now see db.sqlite3 database.


<h3><a id="superuser">4. Create Superuser (Admin)</a></h3>

1. Run command (python manage.py createsuperuser) in the terminal. 
2. Input a username in the terminal (user)
3. Enter an email address
4. Enter a password (password)

This will create a admin user. Run the app (python manage.py runserver). Open the website. Go to admin portal (/admin). Enter the user name and password and you will be able to see the admin page.


<h3><a id="emptyblogapp">5. Set up Empty Blog App</a></h3>

<ol><li>Run command (python manage.py startapp blog). This will create a blog folder with multiple files in it.</li><ol>
<li>Folder - migrations: Here all database changes will be registered. We won't be modifying the migration directory.</li>
<li>__init__.py: This is also not modified normally. This contains initial code that will be run when the blog app starts.</li>
<li>admin.py: Contains code that has to do with admin interface. </li>
<li>apps.py: This is a config file for the app. No changes normallly done here.</li>
<li>models.py: A webpage from a website has three components - model (contains database field).</li>
<li>tests.py: To write tests when the app is ready.</li>
<li>views.py: Second component to serve the website from Django perspective. Is an organizer (middleman) between html code and model. View gets data from model and serve it to html tempelate.</li>
</ol>
<li>Go to mysite directory, an dopen settings.py file. In that file, modify the INSTALLED_APPS part and add a new item to the list 'blog'</li>
</ol>

<h3><a id="blogappwork">6. Blog App Work</a></h3>

<ol>
<li>Modify the models.py file in the blog directory.</li>
<li>To apply above model to our website, run command (python manage.py makemigrations) from the terminal. This will create a database as defined in the class.</li>
<li>To apply the above migration run the command (python manage.py migrate) from the terminal. This will apply the migrations.</li>
<li></li>
<li></li>
<li></li>
<li></li>
<li></li>
<li></li>
<li></li>
</ol>



