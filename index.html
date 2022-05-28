const express = require('express');
const app = express();

const cors = require('cors');
const { param } = require('express/lib/request');

const mongodb = require('mongodb');
const bcrypt = require('bcryptjs');
const jwt = require('jsonwebtoken');

const mongoClient = mongodb.MongoClient;
const URL = 'mongodb://localhost:27017';

app.use(
  cors({
    origin: 'http://localhost:3000',
  })
);
app.use(express.json());

// added
// let students = [];

function authenticate(req, res, next) {
  // Check token present in header
  if (req.headers.authorization) {
    let decode = jwt.verify(req.headers.authorization, 'thisisasecretkey');
    if (decode) {
      req.userId = decode.id;
      next();
    } else {
      res.status(401).json({ message: 'Unauthorized' });
    }
  } else {
    res.status(401).json({ message: 'Unauthorized' });
  }
  // if present
  // check toen is valid
  // if valid
  // next()

  // res.status(401).json({message : "Unauthorized"})
  // next()
}

// Method : GET
// route : /students
// params :
// Body :

// Return
// [{name : ""},{name : ""}]
app.get('/students', authenticate, async (req, res) => {
  try {
    // Open the connection
    let connection = await mongoClient.connect(URL);

    // Select the DB
    let db = connection.db('b32wdt');

    // Select the collection
    // DO operation
    let students = await db
      .collection('students')
      .find({ createdBy: req.userId })
      .toArray();

    // Close the connection
    await connection.close();

    res.json(students);
  } catch (error) {
    console.log(error);
    res.status(500).json({ message: 'Something went wrong' });
  }
});

// Method : POST
// Route : /student
// Params :
// Body : Stuent info

// Return
// Object : Stundet ID
app.post('/student', authenticate, async (req, res) => {
  try {
    let connection = await mongoClient.connect(URL);

    let db = connection.db('b32wdt');
    req.body.createdBy = req.userId;
    await db.collection('students').insertOne(req.body);

    await connection.close();

    res.json({ message: 'Student Added' });
  } catch (error) {
    res.status(500).json({ message: 'Something went wrong' });
  }

  // let id = students.length + 1;
  // req.body.id = id;
  // students.push(req.body);
  // res.json({ id });
});

// Method : PUT
// Route : /student/:id
// Params : :id
// Body : Update info

// Return
// updated object

app.put('/student/:id', authenticate, async (req, res) => {
  try {
    let connection = await mongoClient.connect(URL);

    let db = connection.db('b32wdt');

    await db
      .collection('students')
      .updateOne({ _id: mongodb.ObjectId(req.params.id) }, { $set: req.body });

    await connection.close();

    res.json({ message: 'Student Updated' });
  } catch (error) {
    res.status(500).json({ message: 'Something went wrong' });
  }

  // // Find a student index number by Params id
  // let studentIndex = students.findIndex((obj) => obj.id == req.params.id);

  // // Update the student information
  // req.body.id = students[studentIndex].id;
  // students[studentIndex] = req.body;

  // // Return the updated objecrt
  // res.json(students[studentIndex]);
});

// Method : DELETE
// route : /student/:id
// Parms : id
// Body :

// Return
// Deleted ID
app.delete('/student/:id', authenticate, async (req, res) => {
  try {
    let connection = await mongoClient.connect(URL);

    let db = connection.db('b32wdt');

    await db
      .collection('students')
      .deleteOne({ _id: mongodb.ObjectId(req.params.id) });

    await connection.close();

    res.json({ message: 'Student Deteleted' });
  } catch (error) {
    res.status(500).json({ message: 'Something went wrong' });
  }

  // let studentIndex = students.findIndex((obj) => obj.id == req.params.id);
  // let id = students[studentIndex].id;
  // students.splice(studentIndex, 1);
  // res.json({ id });
});

// Method : GET
// route : /student/:id
// params : id
// Body :

// Return
// Object
app.get('/student/:id', authenticate, async (req, res) => {
  try {
    let connection = await mongoClient.connect(URL);

    let db = connection.db('b32wdt');

    let student = await db
      .collection('students')
      .findOne({ _id: mongodb.ObjectId(req.params.id) });

    await connection.close();

    res.json(student);
  } catch (error) {
    res.status(500).json({ message: 'Something went wrong' });
  }
  // let studentIndex = students.findIndex((obj) => obj.id == req.params.id);
  // res.json(students[studentIndex]);
});

app.post('/register', async (req, res) => {
  try {
    let connection = await mongoClient.connect(URL);
    let db = (await connection).db('b32wdt');

    let salt = bcrypt.genSaltSync(10);
    var hash = bcrypt.hashSync(req.body.password, salt);
    req.body.password = hash;

    await db.collection('users').insertOne(req.body);
    await connection.close();
    res.json({ message: 'User Created' });
  } catch (error) {
    res.status(500).json({ message: 'Something went wrong' });
  }
});

app.post('/login', async (req, res) => {
  try {
    // open the connection
    let connection = await mongoClient.connect(URL);
    // select the db
    let db = connection.db('b32wdt');
    // fetch user with email id from DB
    let user = await db.collection('users').findOne({ email: req.body.email });
    if (user) {
      // if user given password is == user password in db
      let compare = bcrypt.compareSync(req.body.password, user.password);
      if (compare) {
        // Generate JWT token
        let token = jwt.sign(
          { name: user.name, id: user._id },
          'thisisasecretkey',
          { expiresIn: '1h' }
        );
        res.json({ token });
      } else {
        res.status(500).json({ message: 'Credientials does not match' });
      }
    } else {
      res.status(401).json({ message: 'Credientials does not match' });
    }
    // if no?
    // throw err user not found
    // if yes?
    await connection.close();
    // close the connection
  } catch (error) {
    console.log(error);
    res.status(500).json({ message: 'Something went wrong' });
  }
});

app.listen(process.env.PORT || 3001, () => {
  console.log('Web server Started');
});

// What is nodejs
// Why Nodejs
// packages
// OS
// fs
// express
// routes
// route params
// Full CRUD api
// Connecting Mongodb with Nodejs

// User Registration
// User Login
// Recap

// Wireframe
// Design
// API
// HTML & CSS Convertion
// API intergration
