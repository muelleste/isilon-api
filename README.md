# isilon-api
This git repository is for all people, who wants to save time, to use the isilon api. 
I lost a few hours to debug the isilon API.

This document is based on the api in version 8.0.1. 

## Authentication
In this PDF-Sheet we only use the authentication method, which will use the basic method. 
For all, who wants to use the Cookie-Variante: 

> curl -k --header "Content-Type: application/json" -c cookiefile -d @auth.json -X POST  https://"ISILON":8080/session/1/session
 
Now you will find a file "cookiefile", this can be used for the next Calls. 

## Get a Method List
There is no swagger documentation, where you can find a method, where you get recieve a list of methods. 

With the parameter "-u" curl will convert the username and the password to a base64 string. In the REST Call this will be used for authorization header. 
> curl -k -u "username":"password"  -v "https://"ISILON":8080/platform/?describe&list"

The return value will be a List of all Methods, all Methods can be used whith a HTTP GET to get all other methods (POST, GET, PATCH, REMOVE).
 
