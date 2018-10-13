## Express

Ekspress bukan topik utama kita, saat ini maka kita hanya memakai express saja, jika belum mengerti tentang express anda dapat membaca materi express [disini](https://github.com/talkasrul/workshop-express).

### Apa saja route yang kita perlukan?

Sebagai bahan untuk pembelajaran kita, kita hanya membuat rute yang sederhana dan metode yang kita pakai masih **GET** dan **POST** saja dulu, seperti berikut ini.

Route |	Method |	Functionality
------|--------|----------------
/contacts	| GET |	Menampilkan semua data kontak
/contacts	| POST | Menulis kontak baru
/contacts/:id/edit	| GET | Menampilkan 1 kontak sesuai id
/contacts/:id/update	| POST | Menampilkan 1 kontak sesuai id
/contacts/:id/delete	| POST | Menampilkan 1 kontak sesuai id


### Membangun server

```javascript
const express = require('express')
const app = express()
const routes = require('./routes')

app.use(express.urlencoded({extended: false}))
app.use(express.json())

app.use('/', routes)

app.listen('3000', () => console.log('Your server listening on port 3000'))
```

### Membuat route

Buat file `index.js` pada folder routes dengan kode berikut.

```javascript
const router = require('express').Router()
const contacts = require('./contacts.route')

route.use('/contacts', contacts)

module.exports = router
```

Buat juga file yang mengelola rute contact dengan nama `contacts.route.js` dengan kode berikut

```javascript
const router = require('express').Router()
const {
  getAll,
  getOne,
  createOne,
  updateOne,
  deleteOne
} = require('../controller/contact.controller')

route
  .get('/', getAll)
  .get('/:id', getOne)
  .post('/', createOne)
  .put('/:id', updateOne)
  .delete('/:id', deleteOne)

module.exports = router
```

### [Membaca data menggunakan sequelize >>>>](https://github.com/talkasrul/workshop-sequelize/blob/master/learn/05-get-data-sequelize.md)