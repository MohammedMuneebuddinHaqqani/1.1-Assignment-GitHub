# 1.1-Assignment-GitHub
const express = require('express');
const apiRoutes = require('./routes/api');

const app = express();
const port = 3000;

app.use(express.json());

// API Routes
app.use('/api', apiRoutes);

// Basic Error Handling
app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send('Something broke!');
});

app.listen(port, () => {
    console.log(`Server running on http://localhost:${port}`);
});

const express = require('express');
const router = express.Router();

// Example GET endpoint
router.get('/example', (req, res) => {
    res.send('This is a GET example');
});

// Example POST endpoint
router.post('/example', (req, res) => {
    res.send('This is a POST example');
});

module.exports = router;

node app.js
