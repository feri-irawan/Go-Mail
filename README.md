# Go-Mail
Kirim pesan email HTML ke seseorang dengan mudah lewat web kamu sendiri.

Demo 1:
[https://gomail.netlify.app/](https://gomail.netlify.app/ "Go-Mail")
Demo 2:
[https://gomail.epizy.com/](https://gomail.epizy.com/ "Go-Mail")

Cara Menggunakan:
        <form action="http://gomail.epizy.com/mail.php" method="get">
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
       
          <!-- Konfigurasi GoMail -->
          <div id="GoMail">
            <!-- Jenis Pesan -->
            <input value="verify_code" name="message_type">
            
            <!-- Perushaan -->
            <input value="GoMail" name="company_name">
          </div>
        </form>
         