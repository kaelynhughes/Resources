# Troubleshooting Insomnia

## Possible issues:

* If you send a GET request and receive a JSON object with error: bad authentication: 
    * Cookies - delete the big cookie
    * HR -> send a GET request to the Get Authentication Cookie URL
* Don't try to use the Group and Department URLs under Units - we have since switched to using a Unit class rather than having those separate
* If you get a lot of 404 Not Founds, make sure the URL doesn't include /api/ or /v1/ after the base url - both of those are included in the base url variable so it will double them and throw off the URL