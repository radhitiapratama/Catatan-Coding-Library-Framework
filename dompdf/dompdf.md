# Dompdf

Dompdf adalah Library untuk membuat fitur Export Pdf

## Installasi

### Dengan Composer

```bash
composer require dompdf/dompdf
```

require vendor terlebih dahulu jika menggunakan Framework CI 3 jika menggunakan Laravel tidak usah

```php
require_once 'vendor/autoload.php';
```

## Penggunaan

Buatlah Controller dengan nama PdfController untuk contoh di bawah ini menggunakan Framework CI 3

### Controller

```php
<?php

defined('BASEPATH') or exit('No direct script access allowed');

require_once 'vendor/autoload.php';

use Dompdf\Dompdf;

class PdfController extends CI_Controller
{

    public function index()
    {
        //load View
        $this->load->view('pdf');
        
        $dompdf = new Dompdf();

        /*ISI VARIABLE YANG INGIN DI LOAD DI $this->loadHTML
         Wajib kita isi dengan  $this->output->get_output()
         Jika tidak maka akan error
        */
        $html = $this->output->get_output(); 
       
        $dompdf->loadHtml($html);
        //Atur ukuran kertas Pdf
        $dompdf->setPaper('A4', 'potrait');
        $dompdf->render();
        // data.pdf adalah nama file 
        // Attachment False / bisa kita ganti denga  0 berguna agar 
        // file pdf tidak langsung di download tapi bisa kita lihat dulu di browser
        $dompdf->stream('data.pdf', ['Attachment' => false]);
    }
}
```

### View

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        h1 {
            text-align: center;
        }

        .table {
            width: 100%;
            text-align: center;
        }
    </style>
</head>

<body>
    <h1>Data PDF</h1>
    <table border="1" class="table">
        <tr>
            <th>No</th>
            <th>Nama</th>
            <th>Email</th>
            <th>Jurusan</th>
        </tr>
        <tr>
            <td>1</td>
            <td>Alexey</td>
            <td>alexey@gmail.com</td>
            <td>Teknik Informatika</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Alexey</td>
            <td>alexey@gmail.com</td>
            <td>Teknik Informatika</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Alexey</td>
            <td>alexey@gmail.com</td>
            <td>Teknik Informatika</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Alexey</td>
            <td>alexey@gmail.com</td>
            <td>Teknik Informatika</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Alexey</td>
            <td>alexey@gmail.com</td>
            <td>Teknik Informatika</td>
        </tr>
        <tr>
            <td>1</td>
            <td>Alexey</td>
            <td>alexey@gmail.com</td>
            <td>Teknik Informatika</td>
        </tr>
    </table>
</body>

</html>
```
