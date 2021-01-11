# Read: 13 - Local Storage
- With web storage, web applications can store data locally within the user's browser.
- in the past the cookies were used as storage.
- Web storage is more secure, and large amounts of data can be stored locally, without affecting website performance.
- there is some problem in using cookies, which is:
1. are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
1. are included with every HTTP request, thereby sending data unencrypted over the internet (unless your entire web application is served over SSL)
1. are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful
- the new way of storage was in html5
- HTML web storage give us two objects to store data on the user local:
```
1. window.localStorage - stores data with no expiration date
2. window.sessionStorage - stores data for one session (data is lost when the browser tab is closed)
```
