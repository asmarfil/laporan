const express = require('express');
const sqlite3 = require('sqlite3').verbose();
const bodyParser = require('body-parser');
const ejs = require('ejs');

const app = express();
const port = 3000;

// Koneksi ke database SQLite
const db = new sqlite3.Database('./database.db', (err) => {
  if (err) {
    console.error(err.message);
    throw err;
  }
  console.log('Terhubung ke database SQLite');
});

// Middleware
app.use(bodyParser.urlencoded({ extended: true }));
app.use(bodyParser.json());
app.set('view engine', 'ejs');
app.use(express.static('public'));

// Membuat tabel siswa jika belum ada
db.run(`CREATE TABLE IF NOT EXISTS siswa (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  nama TEXT NOT NULL,
  usia INTEGER NOT NULL
)`);

// Routes
app.get('/', (req, res) => {
  db.all('SELECT * FROM siswa', (err, rows) => {
    if (err) {
      console.error(err.message);
      throw err;
    }
    res.render('index.ejs', { siswa: rows });
  });
});

app.get('/add', (req, res) => {
  res.render('add.ejs');
});

app.post('/add', (req, res) => {
  const { nama, usia } = req.body;
  db.run('INSERT INTO siswa (nama, usia) VALUES (?, ?)', [nama, usia], (err) => {
    if (err) {
      console.error(err.message);
      throw err;
    }
    res.redirect('/');
  });
});

app.get('/edit/:id', (req, res) => {
  const { id } = req.params;
  db.get('SELECT * FROM siswa WHERE id = ?', [id], (err, row) => {
    if (err) {
      console.error(err.message);
      throw err;
    }
    res.render('edit.ejs', { siswa: row });
  });
});

app.post('/edit/:id', (req, res) => {
  const { id } = req.params;
  const { nama, usia } = req.body;
  db.run('UPDATE siswa SET nama = ?, usia = ? WHERE id = ?', [nama, usia, id], (err) => {
    if (err) {
      console.error(err.message);
      throw err;
    }
    res.redirect('/');
  });
});

app.get('/delete/:id', (req, res) => {
  const { id } = req.params;
  db.run('DELETE FROM siswa WHERE id = ?', [id], (err) => {
    if (err) {
      console.error(err.message);
      throw err;
    }
    res.redirect('/');
  });
});

// Server listening
app.listen(port, () => {
  console.log(`Server berjalan di http://localhost:${port}`);
});

hasilnya error
