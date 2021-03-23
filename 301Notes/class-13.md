# SENDING FORM DATA

- sending data is not hard at all, the hard part is securing the data.
- the client will send the data from the browser like a post request, and the server will take it as the front end developer put the attribute for the form.
- the most important attributes when we want to send a data are:
1. action:
  - fixed url `www....`
  - relative url`/path`
2. method:
  - get
  - post
- when the data come to the server with get request it will shown in the url, which not we want
- when the data come to the server with post request the data will come throw the body of the request, so we use it
- the data will sent throgh HTTP post request it will not shown for the client
- we send the post request for two reasons:
1. security issues
1. data size for get request is so little
- these ways of sending data are used in python and in other languages