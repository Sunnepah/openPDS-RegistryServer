openPDS - Registry Server
======================================

* What is the Registry Server?
 
    The Registry Server is a trustframework registry (includes users, roles etc..) and is also an OAuth 2.0 registry.

* To get started, you'll need python pip and virtualenv installed on your machine (this probably will require root access)

    >apt-get install python-pip
    
    >apt-get install python-virtualenv

    >virtualenv registryEnv
    
    >cd registryEnv
    
    >source bin/activate
    
    >git clone git@github.com:HumanDynamics/openPDS-RegistryServer.git -b master

    >cd openPDS-RegistryServer
 * Note: In conf/requirements.txt change the following:
    pymongo to pymongo==2.8, django-allauth to django-allauth==0.20.0
    >pip install -r conf/requirements.txt

    >cd registryServer
    
    >python manage.py syncdb
    
    *NOTE: At this point you may get an error 'sqlite3.OperationalError: unable to open database file'
    This occured because the default sqlite database path (/var/www/trustframework/registryEnv/OMS-RegistryServer/test.db) set in settings.py file in your current direcoty doesn't exist on your system yet. To fix, create your sqlite database and set the path in settings.py
    >python manage.py syncdb
    
    >python manage.py runserver 0.0.0.0:8000 (for access to local VM)
    
* The above steps will get you started with a registry server on port 8000 of your machine's loopback interface (for local access only). 
