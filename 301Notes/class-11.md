# Templating "EJS"

- when the server response to hitting the route the response that we was used wich is res.send(...) will send just one thing
- we can use: `res.write(firstThing);
res.write(secondThing);...
res.send()` => in this way also we are sending our data like using email type of sending.
- ok know we can send html file using `res.sendFile(pathOfOurHtmlFile)` => in this way we will do html file for every situation wich is not effiecient at all
- the solution is using templating method wich is "EJS"
- EJS stands for `Embedded JavaScript Templating`
- [Go to EJS documentation](https://ejs.co/)
- [This github page explain how to use EJS with express package](https://github.com/mde/ejs/wiki/Using-EJS-with-Express)
- the ejs file should be inside `views` folder
- the ejs file content is like html file
- `<%= %>` inside this marker you can put the changing data.
- we write this in server.js to render what we want inside ejs file`response.render('nameOfTheEjsFileInsideTheviewsFolder', { keyFromTheEjsFile: valueFromJsFile });`
- you can write code inside ejs file with adding the tagg `<% every line in the code inside ejs file %>`
