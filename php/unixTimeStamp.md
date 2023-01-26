
# Konversi UNIX Time ke Local Date Time 

Supaya waktu data di insert ke database oleh user itu otomatis mengambil waktu Time Zone dari user kita harus menggunakan UNIX Time,misal anggap saja di table kita terdapat field createdAt nah biasanya kita set tipe data dari field tersebut dengan dateTime/date/TimeStamp namun jika aplikasi kita sangat besar bahkan hingga sampai ke luar negri Time Zone nya pasti berbeda jadi misal ada user asalnya dari Russia menginputkan data di jam 07.00 (waktu rusia) nah tetapi di database data yang masuk bukan jam 07.00 tapi jam 11.00 (selisih 4 jam), kenapa ini bisa terjadi ? karena Time Zone kita dengan Russia itu bebeda, bagaimana cara mengatasinya ? ya kita gunakan saja UNIX Time Stamp, jadi kita ubah tipe data dari field CreatedAt menjadi tipe data BigInt/Int

### Contoh UNIX TimeStamp
```php
$unix_timestamp = 1622662400;
```

Jadi angka tersebut yang akan kita masukkan ke dalam database

Supaya saat kita panggil data nya dari database itu menjadi Tanggal dan waktu pada umumnya kita harus Konversi terlebih dahulu

### Berikut Contoh Kode Konversi UNIX TimeStamp menggunakan php

```php
    /**
    Untuk mendapatkan waktu sekarang
    dengan format UNIX TimeStamp anda
    dapat menggunakan round(microtime(true))
    **/

    $unixTime = round(microtime(true));
    $datetime = new DateTime("@$unixTime");

    //Ubah ke Local Time Zone
    $datetime->setTimezone(new DateTimeZone('Europe/Moscow'));

    //Format Menjadi "01-10-2022 12:00:00"
    $timestamp = $datetime->format('d-m-Y H:i:s');
    echo $timestamp;
```

