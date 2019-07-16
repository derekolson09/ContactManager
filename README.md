# ContactManager
This is a react based MERN stack application for managing contacts


## HOST LOCALLY

### NPM RUN DEV

Builds the client and the server on ports 3000 and 5000 respectively. This is watched by nodemon dependency. 
You will need to create your own config folder and inside it have a db.js and a default.json.
Default.json needs to include a MongoDB connection string and the and jwtSecret (encryption key).
db.js needs to include a mongoose connection function that module exports with the name connectDB.
Example db.js:
```js
const mongoose = require('mongoose');
const config = require('config');
const db = config.get('mongoURI');

const connectDB = async () => {
    try {
        await mongoose.connect(db, {
            useNewUrlParser: true,
            useCreateIndex: true,
            useFindAndModify: false
        })

        console.log('MongoDB Connected...')
    } catch (err) {
        console.error(err.message);
        process.exit(1);
    }
};


module.exports = connectDB;
```

example default.json:
```js
{
    "mongoURI": "[INSERT GENERATED MONGO CONNECTION STRING HERE]",
    "jwtSecret": "[INSERT HASH KEY HERE]"
}
```

Good luck and have fun.
