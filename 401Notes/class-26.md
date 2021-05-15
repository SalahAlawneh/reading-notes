# Android Fundamentals
## Generals
- the languages used in android applications are java, kotlin and c++
- SDK stands for software development kit, and it's installable package contain software development tools
- when you install the SDK that the results will be in APK=> android application package, in technical way i can say that the SDK will compile my code with all resources and data to Andoid Application Package.
- the android application package contains all files from android application with .apk suffix, and that what you install in your device
## App components
- the component is an essential building block in any application
- every component can be an entry point to the applicaion
- there is four types of components:
  1. services
  1. activities
  1. Broadcast receivers
  1. Activating component

### Activities
- the activity is an entry point for interacting with a user
- in the activities the interacting will be between the system and the app
- the interacting between activities can be done between different applications
### Services
- the service is an general purpose entry point to the application, and it's done in the bakcground without interface
- there is two type of them, some of them have to be worked until they finish wich is the one the user have to be aware of and in purpose he wanted to run, in the another hand there is services the system can manage it's working, so it can be killed and restart after in the right time.
- one application can use a service from another one, and the service can have an api to provide service to another application
### Broadcast receivers
- a broudcast receiver is an component can make an event outside of user flow experince
- and can be without event running the application
- it doesn't have a user interface, it can havae just a status bar notification
- some of the examples on broudcast receivers are alarm notifcation, finish downlad notification, notifcation to confirm if you are the user done input from another device to your account,...etc
### Content providers
- A content provider manages a shared data that you can store in the file system, in a SQLite database, web, or on any other persistent storage location the app can access.
- there is not single entry point in the android application=> there is not main() function
- URI stands for Uniform resource identifier 
- any android applications can activate the anoter application componets
- every application run on differnet process
- You cannot acces another application component directly, so you will send a message to the app with your intent of the component you want to use, and with this way you can access it
## Activating components
- all of components except the content provider can activated by message called `intent`
- the intent send by `intent` object that define a message to activate:
  1. a component
  1. type of component
- the content provider don't work in the intent way
- the content provider will activated when a reqest resived from contentProvider
