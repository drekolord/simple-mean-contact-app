# Simple Mean Contacts App
Simple application to Add, Update, Remove, Search records using MEAN stack.

Records generated based on field array defined in app.js list.

```javascript
vm.fields = [
    {label: 'Name', key: 'name'},
    {label: 'Email', key: 'email'},
    {label: 'Phone', key: 'phone'}
];
```

Change above array to have your own fields, html generates input box as of now and change below for update query in server.js

```javascript
app.put('/records/:id', function(req, res, next){
    var id = req.params.id;
    records_collection.updateOne(
        {'_id': new ObjectId(id)},
        { $set: {
            'name' : req.body.name,
            'email': req.body.email,
            'phone': req.body.phone
            }
        }, function(err, results){
            console.log(results);
            res.json(results);
    });
});
```

This is for simple seed mean app at it basic level for learning.

To Execute the Application:

Step 1 - install dependencies:

```terminal
npm install 
```
Install dependencies in a VM/vagrant

```terminal
npm install --no-bin-links
```
Step 2 - run the application:

```terminal
node server.js
```
or
```terminal
nodemon server.js
```
### Prerequisites : 
* mongodb to be installed
* nodemon installed globally