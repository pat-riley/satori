##Express Tutorial

[Tutorial Taken from this site](http://cwbuecheler.com/web/tutorials/2013/node-express-mongo/)

1. Find where you want the app to live and enter `express <name of app>`

2. Add MongoDB and Monk to `package.json`

		"mongodb": "*",
		"monk": "*"
3. `npm install` to get those dependancies, this will create a /node_modules folder
4. `mkdir data` will create a data directory where mongo will eventually store data
5. `npm start` and visit localhost:3000 to see you application
6. Add this code to the bottom of `routes/index.js`

		router.get('/helloworld', function(req, res) {
		    res.render('helloworld', { title: 'Hello, World!' })
		});
	This adds another route for a /helloworld page

7. Clone `views/index.jade` and name the new copy `helloworld.jade`
8. Add `p Hello, World! Welcome to #{title}` to the page
9. `npm start` and navigate to `http://localhost:3000/helloworld`
10. Install mongod
11. `mongod --dbpath /Users/pat/workspace/express_test` starts up a mongo server
12. Navigate to Mongo Installation directory `/usr/local/bin` and enter `mongo`
13. `use express_test` switches you to the express_test database
14. Enter the following in the terminal

		db.usercollection.insert({ "username" : "testuser1", "email" : "testuser1@testdomain.com" })
		
		then this 
		
		db.usercollection.find().pretty()
		
		and then this 
		
		newstuff = [{ "username" : "testuser2", "email" : "testuser2@testdomain.com" }, { "username" : "testuser3", "email" : "testuser3@testdomain.com" }] db.usercollection.insert(newstuff);

15. Open `app.js` and add these lines at the top

		var mongo = require('mongodb');
		var monk = require('monk');
		var db = monk('localhost:27017/express_test');
These lines tell our app we want to talk to MongoDB. we are going to use Monk to do it, and our data base is located at localhost:27017/express_test

16. Add the following lines before the route definitions

		// Make our db accessible to our router
		app.use(function(req,res,next){
		    req.db = db;
		    next();
		});
		
17. Add the following code to index.js to establish a route to the db.

		/* GET Userlist page. */
		router.get('/userlist', function(req, res) {
		    var db = req.db;
		    var collection = db.get('usercollection');
		    collection.find({},{},function(e,docs){
		        res.render('userlist', {
		            "userlist" : docs
		        });
		    });
		});
		
	This code is extracting the DB object we passed into our http request, and then using the db connection to fill our "docs" variable with database documents, ie: user data. Then we do a page render just like the other two "gets" in this route file.

	Basically, we tell our app which collection we want to use ('usercollection') and do a find, then return the results as the variable "docs". Once we have those documents, we then do a render of userlist (which will need a corresponding Jade template), giving it the userlist variable to work with, and passing our database documents to that variable.
	
18. Make another directory called `userlist.jade` and edit the HTML so it looks like...

		extends layout

		block content
		    h1.
		        User List
		    ul
		        each user, i in userlist
		            li
		                a(href="mailto:#{user.email}")= user.username

		    
19. `/Users/pat/workspace/express_test>npm start` and open your web browse at `http://localhost:3000/userlist` to see the results

20. Quickly wire up a route for an add user form. Open `/routes/index.js` and add the following code above the last module.exports line:

		/* POST to Add User Service */
		router.post('/adduser', function(req, res) {

		    // Set our internal DB variable
		    var db = req.db;

		    // Get our form values. These rely on the "name" attributes
		    var userName = req.body.username;
		    var userEmail = req.body.useremail;

		    // Set our collection
		    var collection = db.get('usercollection');

		    // Submit to the DB
		    collection.insert({
		        "username" : userName,
		        "email" : userEmail
		    }, function (err, doc) {
		        if (err) {
		            // If it failed, return error
		            res.send("There was a problem adding the information to the database.");
		        }
		        else {
		            // If it worked, set the header so the address bar doesn't still say /adduser
		            res.location("userlist");
		            // And forward to success page
		            res.redirect("userlist");
		        }
		    });
		});
		
21. Test it out, your Live!