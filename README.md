# Go-Mail
Kirim pesan email HTML ke seseorang dengan mudah lewat web kamu sendiri.

*Demo 1:*
[https://gomail.netlify.app/](https://gomail.netlify.app/ "Go-Mail")

*Demo 2:*
[http://gomail.epizy.com/](http://gomail.epizy.com/ "Go-Mail")

## Cara Menggunakan:
Cara menggunakannya sangat mudah, Anda hanya perlu membuat form seperti biasanya. _Tapi Anda juga bisa memanipulasinya menggunakan PHP, JavaScript atau bahasa lain_

Namun ada beberapa nilai atribut <code>action=""</code> dan <code>name=""</code> di tag <code>input</code> yang harus Anda tulis (sangat dibutuhkan). [Lihat nilai yg di izinkan](#nama-input). Contoh:

```html
<form action="http://gomail.epizy.com/mail" method="post">
  <!-- True --> 
  <input type="text" name="name">
  <!-- False --> 
  <input type="text" name="username">
</form>
``` 

Perhatikan pada atribut <code>action=""</code> nilai pada harus di isi dengan <code>http://gomail.epizy.com/mail</code>. Jika tidak, maka formulir tidak akan berfungsi sama sekali. Jangan lupa gunakan `method="post"`

Perhatikan juga pada atribut <code>name=""</code>, input dengan nama <code>username</code>. Untuk saat ini, atribut dengan nama seperti itu tidak akan dikenali oleh Go-Mail dan akan diabaikan. Namun, anda bisa menggantinya dengan <code>name="name"</code>.

Hal tersebut juga berlaku untuk tombol <code>type="submit"</code>. Anda hanya di perbolehkan untuk menggunakan dua nilai dari atribut <code>name</code>, yaitu:
```html   
<button type="submit" name="GoMail">Submit</button>
  <!-- or --> 
<input type="submit" name="GoMail" value="submit"/>
  <!-- and --> 
<button type="submit" name="submit">Submit</button>
  <!-- or --> 
<input type="submit" name="submit" value="submit"/>
```
## Form Configuration
Ada bebrapa konfigurasi yang dapat anda sesuaikan sendiri, seperti jenis pesan, informasi penerima pesan, atau bahkan nama perusahaan pengirim pesan.
```html
<div id="GoMail">
  <!-- Subject -->
  <input value="Go-Mail" name="subject">
  
  <!-- Message Type -->
  <input value="simple" name="message_type">
  
  <!-- Recipient Information -->
  <input value="Feri Irawan" name="destination_name">
  <input value="feriirawans1998@gmail.com" name="email_destination">
  
  <!-- Company -->
  <input value="GoMail" name="company_name">

  <!-- Redirect URL -->
  <input value="URL tujuan" name="redirect_url">
</div>
```

Perhatikan bagain "Message Type" pada kode diatas, input dengan <code>name="message_type"</code> akan dikenali sebagai jenis/type pesan dan tipe ini ditentukan oleh nilai dari atribut <code>value=""</code> yang untuk saat ini hanya dapat diisi dengan <code>value="simple"</code> dan <code>value="verify_code"</code> 

Perhatikan bagian "Recipient Information" pada kode diatas. Jika tujuan anda ingin membuat form kontak untuk seaeorang mengirim pesan kepada anda, anda bisa mengisi nilai dari atribut <code>value</code> sesuai dengan nama anda dan email anda sendiri

Perhatikan bagian "Redirect URL", itu bertujuan agar, jika pesan berhasil di kirim, maka pengguna mau di redirect ke halaman mana. Anda bisa menggunakan halaman web sendiri. (Ini optional)

## Nama Input
Berikut adalah beberapa nama input yang dipebolehkan akan formulir yang anda buat dapat berfungsi dengan semestinya (masih dalam perkembangan).
```html    
    name="name"
    name="last_name"
    name="age"
    name="date_of_birth"
    name="email"
    name="phone"
    name="country"
    name="province"
    name="city"
    name="address"
    name="website"
    name="company_name"
    name="verify_code"
    name="zipcode"
    name="message"
    name="custom_message"
    name="destination_name"
    name="email_destination"
    name="message_type"
```

## Full Code
Berikut ini telah saya sediakan full code HTML untuk menggunakan dua jenis/type pesan yg diperbolehkan.

>CSS by: Bootstrap v5 (required)

## Simple
```html
<h2>Simple Form</h2>
<form action="http://gomail.epizy.com/mail" method="post">
  <div class="mb-3">
    <label for="name">Name</label>
    <input type="text" name="name" class="form-control">
  </div>
  <div class="mb-3">
    <label for="email">Email</label>
    <input type="email" name="email" class="form-control">
  </div>
  <div class="mb-3">
    <label for="message">Message</label>
    <textarea name="message" rows="6" cols="40" class="form-control"></textarea>
  </div>

  <button type="submit" name="GoMail" class="btn btn-primary">Submit <i class="fas fa-paper-plane"></i></button>
 
  <!-- Coiguration GoMail -->
  <div id="GoMail">
    <!-- Subject -->
    <input value="Go-Mail Testing" name="subject">
    
    <!-- Message Type -->
    <input value="simple" name="message_type">
    
    <!-- Recipient Information -->
    <input value="Feri Irawan" name="destination_name">
    <input value="feriirawans1998@gmail.com" name="email_destination">
    
    <!-- Company -->
    <input value="GoMail" name="company_name">

    <!-- Redirect URL -->
    <input value="http://gomail.epizy.com" name="redirect_url">
  </div>
</form>
```

## Verify Code
```html
<h2>Send Verification Code</h2>
<form action="http://gomail.epizy.com/mail" method="post">
  <div class="mb-3">
    <label for="destination_name">To Name</label>
    <input type="text" name="destination_name" class="form-control">
  </div>
  <div class="mb-3">
    <label for="email_destination">To Email</label>
    <input type="email" name="email_destination" class="form-control">
  </div>
  
  <div class="mb-3 col-6">
    <label for="verify_code">Verification Code</label>
    <input type="number" name="verify_code" class="form-control">
  </div>

  <button type="submit" name="GoMail" class="btn btn-primary">Submit <i class="fas fa-paper-plane"></i></button>

  <!-- Configuration GoMail -->
  <div id="GoMail">
    <!-- Message Type -->
    <input value="verify_code" name="message_type">
    
    <!-- Company -->
    <input value="GoMail" name="company_name">
  </div>
</form>
```
## Rilis
v1.0.0 (1/3/21)
 - Rilis

v1.1.0 (26/7/21)
 - Menambahkan redirect URL
 - Pesan redirect

Created 2021 by Feri Irawan
