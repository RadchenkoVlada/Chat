# Chat
## Description
In this chat, such cases are implemented.

* Possibility to chat for 2 people
## Install
The first thing to do is find the directory on your computer in which we will create virtualenv.
In my case env - name of the virtual environment virtualenv, and run:
```
$ python3 -m venv env
$ source env/bin/activate
```
And run:
```
$ pip install -r requirements.txt
```
Then, you'll need Redis running locally; the settings are configured to point to localhost, port 6379, but you can 
change this in the CHANNEL_LAYERS setting in settings.py. Go to the directory where
manage.py file and run:
```
$ python manage.py migrate
$ python manage.py runserver
```
##Usage
Make yourself a superuser account:
```
$ python manage.py createsuperuser
```
Then, log into http://localhost:8000/admin/ and make a couple of Room objects. Be sure to make one that is set to 
"staff-only",

Finally, make a second user account in the admin that doesn't have staff privileges. You'll use this to log into the 
chat in a second window, and to test the authentication on that staff-only room.
Or create the second superuser account.

Now, open a second window in another browser or in "incognito" mode - you'll be logging in to the same site with two 
user accounts. Navigate to http://localhost:8000 in both browsers and open the same chatroom.

At this moment, you can type messages and see them appear on both screens at once. You can join other rooms and try there, and see 
how you receive messages from all rooms you've currently joined.

If you try and make the non-staff user join your staff-only chatroom, you should see an error as the server-side 
authentication code kicks in.

##Where did I get the information
1. Django Channels

Channels is a project that takes Django and extends its abilities beyond HTTP - to handle WebSockets, chat protocols, 
IoT protocols, and more. It’s built on a Python specification called ASGI.
https://channels.readthedocs.io/en/latest/index.html

2.Chat templates: Like Hangout Chat
https://bootsnipp.com/snippets/2zyo

3.
