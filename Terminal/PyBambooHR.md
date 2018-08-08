# PyBambooHR Module

Unofficial Python API for Bamboo HR
Requires Requests library for Python and HTTPrety for testing.

## Installation of Requests

Download Homebrew
Install pipenv
    
    $ brew install pipenv
    
Install requests

    $ pipenv install requests
    
Get the Source Code    
    
    $ git clone git://github.com/requests/requests.git
    
Embed in Python package

    $ cd requests
    $ pip install .
    
 ## Install HTTPretty for testing
 0.9.5
 Python Support: 2.7.13/ 3.6.5
 
 Install 
    
    pip install httpretty
    
 ## Using the Library 
    
    from PyBambooHR import PyBambooHR
    bamboo = PyBambooHR(subdomain='sambatv', api_key='apiKey')
    employees = bamboo.get_employee_directory()
