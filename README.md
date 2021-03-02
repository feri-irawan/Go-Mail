# Go-Mail
Kirim pesan email HTML ke seseorang dengan mudah lewat web kamu sendiri.

Demo 1:
[https://gomail.netlify.app/](https://gomail.netlify.app/ "Go-Mail")

Demo 2:
[https://gomail.epizy.com/](https://gomail.epizy.com/ "Go-Mail")

## Cara Menggunakan:
Cara menggunakannya sangat mudah, Anda hanya perlu membuat form seperti biasanya.

Namun ada beberapa nilai atribut <code>action=""</code> dan <code>name=""</code> di tag <code>input</code> yang harus Anda tulis (sangat dibutuhkan). [Lihat nilai yg di izinkan](#nama-input). Contoh:

```html
<form action="http://gomail.epizy.com/mail.php" method="post">
  <!-- True --> 
  <input type="text" name="name">
  <!-- False --> 
  <input type="text" name="username">
</form>
``` 
Perhatikan pada atribut <code>action=""</code> nilai pada harus di isi dengan <code>http://gomail.epizy.com/mail.php</code>. Jika tidak, maka formulir tidak akan berfungsi sama sekali.

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
  <!-- Message Type -->
  <input value="simple" name="message_type">
  
  <!-- Recipient Information -->
  <input value="Feri Irawan" name="destination_name">
  <input value="feriirawans1998@gmail.com" name="email_destination">
  
  <!-- Company -->
  <input value="GoMail" name="company_name">
</div>
```

Perhatikan bagain "Message Type" pada kode diatas, input dengan <code>name="message_type"</code> akan dikenali sebagai jenis/type pesan dan tipe ini ditentukan oleh nilai dari atribut <code>value=""</code> yang untuk saat ini hanya dapat diisi dengan <code>value="simple"</code> dan <code>value="verify_code"</code>  
Perhatikan bagian "Recipient Information" pada kode diatas. Jika tujuan anda ingin membuat form kontak untuk seaeorang mengirim pesan kepada anda, anda bisa mengisi nilai dari atribut <code>value</code> sesuai dengan nama anda dan email anda sendiri

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

## Rilis
v1.0.0 (1/3/21)

Created 2021 by Feri Irawan