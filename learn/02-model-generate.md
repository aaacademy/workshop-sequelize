## Model Generate

Membuat model menggunakan sequelize menggunakan perintah berikut

```
sequelize model:generate --name Contact --attributes firstName:string,lastName:string,phone:string,email:string
```

**Keterangan**

`--name`: mendefenisikan nama file model yang akan digenerate oleh sequelize dan jika menjadi tabel akan berubah menjasi `plural`, misal: Contact akan menjadi Contacts

`--attributes`: mendefinisikan apasaja field-field yang ada pada tabel yang akan ditulis

Setelah menekan tombol `Enter`, Anda akan mendapatkan file `contact.js` dengan isi sebagai berikut.

```javascript
'use strict';
module.exports = (sequelize, DataTypes) => {
  const Contact = sequelize.define('Contact', {
    firstName: DataTypes.STRING,
    lastName: DataTypes.STRING,
    phone: DataTypes.STRING,
    email: DataTypes.STRING
  }, {});
  Contact.associate = function(models) {
    // associations can be defined here
  };
  return Contact;
};
```

Pastikan tidak ada atribut yang salah pada model, jika sudah yakin benar maka tulis model tersebut menjadi tabel pada database, dengan cara:

```
sequelize db:migrate
```

Cek proses tersebut pada Browser DB, jika mendapatkan hasil seperti gambar berikut maka saya ucapkan **SELAMAT**

![Tabel Contacts](https://github.com/talkasrul/workshop-sequelize/blob/master/img/tableContact.png?raw=true)

### [Seed Generate >>>>](https://github.com/talkasrul/workshop-sequelize/blob/master/learn/03-seed-generate.md)