# Django-Bootstrap Blog and Translator App

There are multiple web frameowkrs available in Python:
1. Django: Easier to work with databases with Django. Django also allows adding more apps within the website.
2. Flask: Building small web applications for emaple translator or converting images to different format, or simpler blogs.
3. JustPy: New framework. Doesn't require html and css knowledge to build a website. This also means its not very flexible. Not good for working with databases. 

<h2>Index</h2>

[1. Virtual Environment](#venv)

[2. Django Project](#djangoproject)

[3. Create Superuser (Admin)](#superuser)

[4. Set up Empty Blog App](#emptyblogapp)

[5. Blog App Work](#blogappwork)

[6. Django App Structure](#djangoappstructure)

[7. Create Admin Portal for Blog Posts](#createadminportal)

[8. Add Home Page](#homepage)

[9. Steps to build App](#trasnslatorapp)


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


<h3><a id="superuser">3. Create Superuser (Admin)</a></h3>

1. Run command (python manage.py createsuperuser) in the terminal. 
2. Input a username in the terminal (user)
3. Enter an email address
4. Enter a password (password)

This will create a admin user. Run the app (python manage.py runserver). Open the website. Go to admin portal (/admin). Enter the user name and password and you will be able to see the admin page.


<h3><a id="emptyblogapp">4. Set up Empty Blog App</a></h3>

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

<h3><a id="blogappwork">5. Blog App Work</a></h3>

<ol>
<li>Modify the models.py file in the blog directory.</li>
<li>To apply above model to our website, run command (python manage.py makemigrations) from the terminal. This will create a database as defined in the class.</li>
<li>To apply the above migration run the command (python manage.py migrate) from the terminal. This will apply the migrations.</li>
<li>Craete a new directory (templates) in DJANGO-BOOTSTRAP-BLOG-.. folder and create a new file blog.html.</li>
<li>Write a standard blog template within the blog.html file. This will be used for all blog posts.</li>
<li>To tell the webiste where the templates are, we need to add a new line in mywite/settings.py (TEMPLATES_DIR = os.path.join(BASE_DIR, 'templates')). Also edit the TEMPLATES list in the settings.py file and add the new TEMPLATES_DIR variable to 'DIRS' key.</li>
<li>The html template will be connected with content with the view.py class. In blog//views.py create a BlogView class to connect html template to data.</li>
<li>To test out the website, we will add a sample blog post using the DB Browser for SQLite app. Dogs blogpost was entered manually. Ideally new blog posts should be entered through the admin portal.</li>
<li>Create a new urls.py file in blog and add a urlpatter in it. Similarly, then go to urls.py file in mysite directory and add newly created urlpatter in blog/urls.py to the urlpatter.</li>
<li></li>
<li></li>
</ol>

<h3><a id="djangoappstructure">6. Django App Structure</a></h3>

<img src="./images/djangoapp_structure.png" alt="Django App Structure"/>

<ol>
<li>User sees example.com/dogs blogpost link.</li>
<li>As developers, we will see html template with code.</li>
<li>db.sqlite3 blog_post table will have each row as one blog post. HTML will insert the required information from table and render them in browser. </li>
<li>models.py is used to define the class of the blog post.</li>
<li>urls.py contains the links of the blog. If the url is find then it notify the views.py</li>
<li>views.py will have a Blog class. This will take care of creating the html template that will be served to the user.</li>
<li>admin interface isused to populate data in blog_post table.</li>
<li>If we had another page say contact us in website, it will have a different html format, a new class contact in models.py and a new table to store the information.</li>
</ol>

    
<h3><a id="createadminportal">7. Create Admin Portal for Blog Posts</a></h3>
In admin.py file in blog directory, add (admin.site.register(Post)) line after importing Post class. This will allow us to edit blog posts from admin portal.

<h3><a id="aboutpage">9. Add About Page</a></h3>

<ol>
<li>Create a new "about.html" page in templates directory and edit it.</li>
<li>In blog//views.py create a ABOUTVIEW class for about.html page.</li>
<li>In blog//urls.py, add a reference to about.html page.</li>
</ol>


<h3><a id="homepage">8. Add Home Page</a></h3>

<ol>
<li>Create a new "index.html" page in templates directory and edit it.</li>
<li>In blog//views.py create a PostList class for index.html page.</li>
<li>In blog//urls.py, add a reference to index.html page.</li>
</ol>


<h3><a id="trasnslatorapp">9. Steps to build App</a></h3>
<p>Follow below steps when creating a new app.</p>
<ol>
<li>Research is it possible?</li>
<li>Create empty Django app.</li>
<li>Top-bottom approach: <ol>
<li>Craete html templates fromuser's perspective.</li>
<li>Configure URLs.</li>
<li>Create views.</li>
<li>Create models.</li>
<li>Connect the processing (Translation) part.</li>
</ol></li>
</ol>
