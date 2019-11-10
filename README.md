# Instalasi-API-server---Instalasi-CodeIgniter-HMVC-RESTful-API

lanjutan dari video sebelumnya 
1. Instalasi API server - Instalasi XAMPP + PostgreSQL
link : https://www.youtube.com/watch?v=3rS-u...  ATAU  https://youtu.be/3rS-uHcc7lY

3. Download CodeIgniter dari situs resminya https://codeigniter.com/
   (versi terbaru saat ini Version 3.1.10)
   a. extract here CodeIgniter-3.1.10.zip
   b. buat folder api pada working directory kita, yaitu
  D:\xampp\htdocs
   c. copy isi folder CodeIgniter-3.1.10, yaitu
      - folder Application, dan folder System 
      - dan file .editorconfig, .gitignore, composer.json dan index.php
   d. paste ke dalam working directory kita yaitu folder api (D:\xampp\htdocs\api) yang telah kita buat
      pada poin b.
   e. test running
      - aktifkan xampp webserver dengan klik xampp-control.exe pada folder D:\xampp
      - klik start apache module
   f. buka browser, ketik http:/localhost/api

4. Download HMVC dari situs resminya https://bitbucket.org/wiredesignz/cod...
   a. extract here wiredesignz-codeigniter-modular-extensions-hmvc-f77a3fc9a6fd.zip
   b. copy isi folder wiredesignz-codeigniter-modular-extensions-hmvc-f77a3fc9a6fd, yaitu
      - folder core, dan folder third_party
   c. paste ke dalam working directory kita yaitu folder api (D:\xampp\htdocs\api) yang telah kita buat
   d. buka browser, ketik http:/localhost/api  
      akan muncul error
          A PHP Error was encountered
   Severity: 8192
   Message: strpos(): Non-string needles will be interpreted as strings in the future. Use an explicit chr() call to preserve the current behavior
   Filename: MX/Router.php
   Line Number: 239
      
   Buka file Router.php pada folder D:\xampp\htdocs\api\application\third_party\MX   
   pada Line Number: 239 
      ganti   
    if (strpos($class, $suffix) === FALSE)
          dengan 
                if ($suffix && strpos($class, $suffix) === FALSE)

   akan muncul error berikutnya
   An uncaught Exception was encountered
   Type: Error
   Message: Call to undefined method MY_Loader::_ci_object_to_array()
   Filename: D:\xampp\htdocs\api\application\third_party\MX\Loader.php
   Line Number: 300 
 
      Buka file Loader.php pada folder D:\xampp\htdocs\api\application\third_party\MX   
   pada Line Number: 300 
 
 protected function _ci_object_to_array($object) 
 { 
  return is_object($object) ? get_object_vars($object) : $object; 
 }
 
      save file setelah ditambahkan
   e. refresh browser Jika tanpa error, maka Anda telah berhasil menginstall HMVC


5. Download RESTful API dari situs resminya https://github.com/chriskacerguis/cod...
   a. klik Clone or download button, klik Download ZIP
   b. extract zip folder codeigniter-restserver-master.zip 
   c. copy isi folder codeigniter-restserver-master, satu per satu ke folder D:\xampp\htdocs\api\application
   d. buka browser, ketik http:/localhost/api 
   e. Jika muncul Rest Server Test maka instalasi RESTful API Server sudah berhasil

dilanjutkan pada tutorial berikutnya
3. Tutorial RESTful API + XAMPP + PostgreSQL + CodeIgniter + HMVC
link : https://youtu.be/LTHqMxa4TA4 ATAU https://www.youtube.com/watch?v=LTHqM...
