# URLShortener

URL Shortening Service:

Things I have done:
1) Implemented the PhishingAPI using the object oriented programming (Data Encapsulation)  to restrict the access of API key, methods and other variables. This prevents the direct modification of the data.
2) Used the Django framework which is a MVC architecture used as a template(MTV), this is used to make web service calls in the backend.
3) Since the service sees 50 or more new URLs per second we need to keep track of the previously used URls, so I have implemented memcachier to hold the previous records. This helps in increasing the preformance of the service upon dealing with the URLs or that were previously checked.
4) There might be duplicate requests coming from the same URL to request the service to handle such requests, I have implemented indexing. Indexing also helps in speedy retrieval from the DB.

Endpoints:

API call check(url)  transforms it into base64 encoding and checks the given  url against the list of known phishing URLs from the phsih Tank, Upon receiving the hash from the PhishTank the hash is sent to the link function which in turn checks and creates the short url using the shortner algorithm. This algorithm decodes the string obtained from the phishtank and enumerate the given string with dictionary characters and encodes the result send the shortend URL to the user.

To implement service on your local instance, please follow the steps.
1) Clone the repository in to your local system.
2) Make sure python is installed on your system, I strongly recommend to use the virtual environment as not to disturb the python library versions on your system.
3) To create a virtual environment in the directory please type following commands into the terminal:
        
        $sudo apt-get install python3-pip
        
        $pip install virtualenv 
        
        $virtualenv -p python3 env
        
        $source env/bin/activate ( follow step 4) 

once you are done with the project type “deactivate” to deactivate the environment.

4) Go to the project directory and install the dependencies using requirements.txt file
       
       $pip install -r requirements.txt

5) once installed run the application using,
       
       $python manage.py runserver localhost:8888

point your browser to http://localhost:8888


