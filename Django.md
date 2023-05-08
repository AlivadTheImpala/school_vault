#python
Back to [[Python]]
***
- [[Django Commands]]
- [[Django Admin]]
- [[URL Mapping]]
-  [[Views]]
- [[Templates]]
- [[Models]]

# Creating a Project and an App
1st step is to create a virtual environment. In python 3.4+ this is a built in module called venv. in the command line, navigate to where you would like to install the virtual environment and enter the following to create the directory.
```python
# to create the venv
python3 -m venv <directoryname>
# to activate the env
source <directoryname>/bin/activate
```

- ``django-admin startproject nameOfProject`` 
- ``django-admin startapp nameOfApp`` 
	- ``python3 manage.py migrate ``
	- create a superuser at this point `` python3 manage.py createsuperuser
