---
layout: post
title:  "membuat web dinamis dengan node js,mysqli crud biodata siswa"
date:   2024-02-05 14:40:37 +0800
categories: jekyll 
---
Untuk membuat web dinamis dengan Node.js dan MySQL, Anda dapat mengikuti langkah-langkah umum berikut ini. Proses ini melibatkan beberapa tahap, seperti membuat database, mengatur server Node.js, dan mengembangkan aplikasi web dengan Express.js. Saya juga akan memberikan contoh sederhana CRUD (Create, Read, Update, Delete) untuk biodata siswa.

Langkah 1: Persiapkan Proyek

Buat folder untuk proyek Anda dan masuk ke dalamnya:


mkdir web-dinamis-nodejs-mysql
cd web-dinamis-nodejs-mysql
Inisialisasi proyek Node.js:


npm init -y
Langkah 2: Install Paket-paket yang Diperlukan

Install Express dan MySQL:


npm install express mysql
Install body-parser untuk membaca data dari formulir:


npm install body-parser
Langkah 3: Buat Database MySQL dan Tabel

Buat database MySQL dan tabel untuk menyimpan biodata siswa:


CREATE DATABASE IF NOT EXISTS school_db;
USE school_db;

CREATE TABLE IF NOT EXISTS students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    age INT,
    grade INT
);
Langkah 4: Buat Server Node.js

Buat file app.js atau index.js:

javascript
Copy code
const express = require('express');
const mysql = require('mysql');
const bodyParser = require('body-parser');

const app = express();
const port = 3000;

// Koneksi ke database MySQL
const db = mysql.createConnection({
    host: 'localhost',
    user: 'root',
    password: 'password',
    database: 'school_db'
});

db.connect((err) => {
    if (err) {
        console.error('Koneksi ke MySQL gagal: ' + err.stack);
        return;
    }
    console.log('Terhub



