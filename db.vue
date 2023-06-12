const mysql = require('mysql2');

const connection = mysql.createConnection({
  host: 'localhost',
  user: 'jbq',
  password: 'Mariadb123*',
  database: 'tiusr2pl_agenda'
});

module.exports = connection;
