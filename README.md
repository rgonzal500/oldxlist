# xlist
xlist - Find craigslist stuff in different cities
## setup
	pip install -r requirements.txt;pip install -r requirements_dev.txt;

	installing lxml in ubuntu requires:

	"""
	sudo apt-get install libxml2-dev libxslt-dev
	sudo apt-get install python-lxml
	"""
## usage
xlist command line currently supports 1 command, find

	Find by 1 category and 1 keyword:
	    python xlist.py find -X sof -K java

	Find by multiple categories and multiple keywords in a specific city:	
	    python xlist.py find -X "sof,web" -K "clojure,node" -C boston

	Args:
	   -X, --categories    Craigslist categories (sof for software jobs - http://city.craigslist.org/sof)
	   -K, --keywords      Keywords/Search to look for; comma separated string.
	   -C, --cities	    Specific cities to search

	-X and -K are required, other args are optional.
## REST Service
xlist supports http GET to retrieve craigslist items:

	ie:
    	curl -u admin:simonese http://localhost:8080/boston/sof?k=python

    k - Comma separated list of keywords
    c - Comma separated list of cities
