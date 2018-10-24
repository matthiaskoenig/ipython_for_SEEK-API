# SEEK API
Example ipython notebook to use the SEEK writeAPI (SEEK version 1.6.0+, https://github.com/seek4science/seek).
 
Creates a `Project --> Investigation --> Study --> Assay(s) --> Assets`, all based on each other, which result in the following ISA structure:
![alt text](https://raw.githubusercontent.com/hleonov/ipython_for_SEEK-API/master/ISA_Structure.png)

The Event and the Publication are not included in the code (Event is possible to add, Publication is not yet in the writeAPI code). 

In addition, contains examples on how to POST assets both based on uploads, or remote URLs, and an Assay with links to pre-existing assets.

'token' should contain a base64 encrypted "username:password" string to your SEEK instance.


## Installation
Setup python virtual environment
```
mkvirtualenv seek --python==python3.6
(seek) pip install -r requirements.txt --upgrade
(seek) pip install jupyterlab
(seek) python -m ipykernel install --user --name seek --display-name "seek"
(seek) jupyter lab
```

## API token
For the connection with the database an API token is required.
Make sure this token is not tracked in the repository.

```
echo -n 'user:password' | base64 > token
```

