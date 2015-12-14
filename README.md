# fog - a foreigners online guide

Have you ever been new to a country of which you did not speek the language and needed a good restaurant, a governmental institution or a doctor, where someone understand your language or at least english? You could search for it online, but how do you do it, if you do not know the language? fog, a foreigners online guide tries to help you to clear that thick fog you have in the beginning!

fog is a online map, where speakers of other languages can share theire experiences with these kind of problems and where you can look for a solution to your problem.

## installing the application

### preparations

#### Python & npm

Make sure you have the latest version of python 2.7 or python 3.4 installed.

#### pip, virtualenvwrapper

If you want to setup and start the backend, you have to install django and it's requirements. To do so, it is recommended to install and use the python package manager `pip`. For the installation, you need root privileges:

```
$ curl -O https://raw.github.com/pypa/pip/master/contrib/get-pip.py
$ pip install virtualenv
```

With pip, you now can install `virtualenv`. This is a tool to create a python environment without messing with your system packages. To make the use of `virtualenv` easier, it is recommended to install `virtualenvwrapper`:

```
$ pip install virtualenv
$ mkdir .virtualenvs
$ pip install virtualenvwrapper
```

You now only have to configure `virtualenvwrapper`. To do so, add the following lines into your `.bashrc` or `profiles`:

```
export WORKON_HOME=$HOME/.virtualenvs
source /usr/local/bin/virtualenvwrapper.sh
```

Finally, reload the `.bashrc` by running the following command:

```
$ source .bashrc
```

### creating the virtualenv and installing requirements

Now you can use the virtualenvwrapper to create a new virtualenv:

```
$ mkvirtualenv fog
```

You now see your prompt prefixed with the current virtualenv. You can deactivate it with `deactivate`. To reactivate it later on, simply use `workon fog`.

To install all requirements and its dependencies, just run the following command:

```
make develop
```

### setup database

To setup the database, there is also a make target:

```
make create-db-user
make create-db
```

To install all database tables, simply run

```
make migrate
```
