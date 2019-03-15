##Setting Up Enviornment##
1. Create a [virtual environment and install Django](https://docs.djangoproject.com/en/2.1/howto/windows/)
2. Start a project "todoapp" in the virtual enviornment
`django-admin.py startproject todoapp
`
This has created a **todoapp** directory. Use the command `cd todoapp` to go into the directory.
3. Create a django app that holds the model and admin 
`manage.py startapp todolist
`
In the file location see if there is a `todoapp` and` todolist` folder and a script name `manage.py`. 
4. Run server on URL use this command 
`manage.py runserver 8100
`
5. A "congratulation" django page will open this ensures that the setup is error free. Repeat steps in case of error.

##Setup Database##
1. [Install Postgresql](https://tutorial-extensions.djangogirls.org/en/optional_postgresql_installation/) 
2. [create database](https://www.guru99.com/postgresql-create-database.html)
3. Create a `templetes` folder in this our `html` files will be stored. 
4. See pgAdmin 4 if database is working properly.

##Main##
1. So open the `settings.py` file in the `todoapp `directory with any text editor of your choice (I prefer `notepad++`).
Open settings.py. 
a. The first thing you need to do is to add the created app “todolist” in the INSTALLED_APPS.
b. Use the above `TEMPLETE` code. 
c. Add `'whitenoise.middleware.WhiteNoiseMiddleware'` in `MIDDLEWEAR` to avoid white noise error. 
d. Also add code for `PROJECT_ROOT`,`STATIC_ROOT` and `STATICFILES_STOREAGE` . 
e. Add this for PostgreSQL

`DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'todoapp',# name of your data base
        'USER': '',# pgsql username
        'PASSWORD': '',# pgsql password
        'HOST': 'localhost',
        'PORT': '5432',
    }
}`

**Thats all for settings.py** 
2. Use model.py script available above.
3. Create migration using the command line with the command below:
`manage.py makemigrations`
then migrate the migrations with the code below.
`manage.py migrate`
it will Apply all migrations: admin, auth, contenttypes, sessions, todolist and will check if its `...OK`
4. Create user id for the Django administration
it will ask you to put **Username, email Id, password and reconfirmation of the password**. A message `Superuser created sucessfully` will get displayed upon successful. 
![image](https://user-images.githubusercontent.com/42100536/54427369-502b3a00-4740-11e9-924e-5e4f8abbc07a.png)
5. Run Server again `manage.py runserver 8100` 

![image](https://user-images.githubusercontent.com/42100536/54427559-e0697f00-4740-11e9-8326-fe5aa0647648.png)
6. Use `View`, `urls`, `admin` and `templete` as per above code. 
7. Just create a` static `folder in the todolist app directory then you can create the` css`folder . place the css code in Notepad++ rename it as `style.css`.
**That’s all for the coding and settings.**
8. Type `manage.py runserver 8100` in the command promt. This shall appear
![image](https://user-images.githubusercontent.com/42100536/54428317-20c9fc80-4743-11e9-8472-09f8dd9ed4db.png)
## Create Catagories##
1. Go to  http://localhost:8100/admin 
2. A credential windows will appear. Enter your Django superuser username and password
![image](https://user-images.githubusercontent.com/42100536/54428504-b6658c00-4743-11e9-9c3d-22561d350647.png)
3. After logging in the page will appear:
click on add categories.
![image](https://user-images.githubusercontent.com/42100536/54428558-e01eb300-4743-11e9-8c94-937131014b7a.png)

4. List of the categories.
![image](https://user-images.githubusercontent.com/42100536/54428681-3c81d280-4744-11e9-9885-c9d936f07dac.png)

##Adding and Deleting Todos##
The App window will look like this...
![image](https://user-images.githubusercontent.com/42100536/54428843-bfa32880-4744-11e9-86e9-98b12598a33e.png)

Thank You!
