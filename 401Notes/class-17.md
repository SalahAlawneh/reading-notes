# Spring Authorization
## Single Sign On With GitHub   
=> that will be using github aunthentication
- Creating a New Project
- Add a Home Page
```
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <title>Demo</title>
    <meta name="description" content=""/>
    <meta name="viewport" content="width=device-width"/>
    <base href="/"/>
    <link rel="stylesheet" type="text/css" href="/webjars/bootstrap/css/bootstrap.min.css"/>
    <script type="text/javascript" src="/webjars/jquery/jquery.min.js"></script>
    <script type="text/javascript" src="/webjars/bootstrap/js/bootstrap.min.js"></script>
</head>
<body>
	<h1>Demo</h1>
	<div class="container"></div>
</body>
</html>
```   
=> we will JQuery

- Securing the Application with GitHub and Spring Security=> just by adding the dependencie
- Add a New GitHub App
```
 	The default redirect URI template is {baseUrl}/login/oauth2/code/{registrationId}. The registrationId is a unique identifier for the ClientRegistration. 
```
in `application.yml`   
```
 	spring:
  security:
    oauth2:
      client:
        registration:
          github:
            clientId: github-client-id
            clientSecret: github-client-secret
```
     
     => replace `github-client-id` with the client id and `github-client-secret`


## Add a Welcome Page   
=> you can render using server side or client side
- Conditional Content on the Home Page

```
@SpringBootApplication
@RestController
public class SocialApplication {

    @GetMapping("/user")
    public Map<String, Object> user(@AuthenticationPrincipal OAuth2User principal) {
        return Collections.singletonMap("name", principal.getAttribute("name"));
    }

    public static void main(String[] args) {
        SpringApplication.run(SocialApplication.class, args);
    }

}
```
- The `/user` Endpoint
- Making the Home Page Public
## Add a Logout Button
- Client Side Changes
- Adding a Logout Endpoint
- Adding the CSRF Token in the Client
- Ready To Roll!
## Login with GitHub
- Initial setup
- Setting the redirect URI
- Adding the Client Registration
- Adding the Login Link
### How to Add a Local User Database?


## Adding an Error Page for Unauthenticated Users
- Switching to GitHub
- Detecting an Authentication Failure in the Client
- Adding an Error Message
- Generating a 401 in the Server
