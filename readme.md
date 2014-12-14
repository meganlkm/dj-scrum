scrumboard
==========


This repository was originally forked from [mahongquan/scrumboard](https://github.com/mahongquan/scrumboard). I have upgraded the package to django 1.7 and plan to change/add features.


## Installation:

#### via git

````
git clone https://github.com/meganlkm/scrumboard.git
cd scrumboard
````

#### environment variables

````
export DJANGO_SETTINGS_MODULE="scrumboard.settings.local"
````

#### install requirements

````
pip install -r requirements.txt
````

#### install schema

````
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
````

## tastypie error

Edit `$PYTHON_LIB_PATH/site-packages/tastypie/resources.py` (~ line 2200)

Change the decorator of `patch_list()` from `@transaction.commit_on_success()` to `@transaction.atomic()`

See this SO answer [http://stackoverflow.com/a/22511270/2055887](http://stackoverflow.com/a/22511270/2055887)
