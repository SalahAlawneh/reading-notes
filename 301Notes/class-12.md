# EJS PARTIALS
- Partials in EJS used when we want to use part of html in a lot of pages.
- common part that are resued in all html pages is the header and the footer and the navigation bar.
- the directory that we will put the partials inside is `views/partials/nameOfPartial.ejs`
- every line in non html syntax have to be inside <% %>
- after doing the partial files we can add it in the file we want with this syntax `<%- include(nameOfPartialEjs) %>`
