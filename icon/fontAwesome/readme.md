# Installasi

Donwload Font Awesome [DI SINI](https://fontawesome.com/download) lalu pilih yang **Free For Web** jika download sudah selesai lalu extract,
Lalu hapus semua folder kecuali Folder  **CSS** dan **WebFonts**\
di dalam folder **CSS** hapus semua file kecuali file **all.min.css**, jika sudah buat folder baru bernama **Icon** lalu copy folder **CSS** dan **WebFonts** ke dalam folder **Icon**, setelah sudah buat file dengan nama ***index.html*** lalu di bagian head tambahkan link ke file **all.min.css**
### Contoh 

```html
<link rel="stylesheet" href="Icon/css/all.min.css">
```

### Penggunaan
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="assets/icon/fontAwesome/css/all.min.css">
</head>

<body>
    <i class="fa-brands fa-instagram"></i>
    <i class="fa-solid fa-pencil"></i>
    <i class="fa-solid fa-house"></i>
    <i class="fa-solid fa-user"></i>
</body>

</html>
```

