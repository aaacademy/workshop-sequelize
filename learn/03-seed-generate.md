## Seed Generate

Seed merupkaan pengisian data awal pada tabel sebuah database

```
sequelize seed:generate --name seed-contact
```

Pada file `seed-contact` ubah menjadi seperti berikut ini:

```javascript
'use strict';

module.exports = {  
  up: (queryInterface, Sequelize) => {
   return queryInterface.bulkInsert('Contacts', [{
      firstName: 'Asrul',
      lastName: 'Harahap',
      phone: '111-222-3333',
      email: 'talkasrul@gmail.com',
      createdAt: new Date(),
      updatedAt: new Date()
    }, {
      firstName: 'Arul',
      lastName: 'Simalango',
      phone: '444-555-6666',
      email: 'arul@mail.com',
      createdAt: new Date(),
      updatedAt: new Date()
    }, {
      firstName: 'Gusti',
      lastName: 'Andrean',
      phone: '777-888-9999',
      email: 'gusti@mail.com',
      createdAt: new Date(),
      updatedAt: new Date()
    }], {});
  },

  down: (queryInterface, Sequelize) => {
   return queryInterface.bulkDelete('Contacts', null, {});
  }
};
```

Setelah data awal selesai, lakukan perintah berikut untu menuliskan kedalam tabel database
```
sequelize db:seed:all
```
Jika mendapatkan hasil seperti berikut ini maka saya ucapkan **SELAMAT**

![Data Seed](https://github.com/talkasrul/workshop-sequelize/blob/master/img/dataSeed.png?raw=true)

### [Kolaborasi Sequelize dengan Express >>>>](https://github.com/talkasrul/workshop-sequelize/blob/master/learn/04-express.md)