# Spring Authentication
- application securit done with two concepts:
  - Authentication
  - Authorization
- Authentication mean who's allowed to get to the App
- Authorization mean the one who allowed to get to App, what's he allowed to do
- Some times Autherization called ==> access control
- main authentication interface is `AuthenticationManager`   
```
public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}
```
- the only method that interdace have is `authenticate`
- the exception is thrown here is a run time exception, thats mean the web will work but it will not give the user the ability to access it, and it will sen 401 http status to server
- common implementation on AuthenticationManager is => `ProviderManager`
```
public interface AuthenticationProvider {

	Authentication authenticate(Authentication authentication)
			throws AuthenticationException;

	boolean supports(Class<?> authentication);
}
```
![](img/16a.png)
- the common helper to AuthenticationManager is `AuthenticationManagerBuilder`
```
@Configuration
public class ApplicationSecurity extends WebSecurityConfigurerAdapter {

  @Autowired
  DataSource dataSource;

   ... // web stuff here

  @Override
  public void configure(AuthenticationManagerBuilder builder) {
    builder.jdbcAuthentication().dataSource(dataSource).withUser("dave")
      .password("secret").roles("USER");
  }

}
```
- the web security in spring is based on `Servlet=filter`=> as you can see in the comming image
![](img/16b.png)
- in order to understand web security you have to make sure understanding these consepts:
   - Creating and Customizing Filter Chains
   - Request Matching for Dispatch and Authorization
   - Combining Application Security Rules with Actuator Rules
   - Method Security
   - Working with Threads
   - Processing Secure Methods Asynchronously
- in spring web security there is main filter, and that filter delegate cahin of internal filters
![](img/16c.png)