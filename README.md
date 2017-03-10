# Laravel Workshop
## Event & Listener

Event  =  peristiwa apa yang terjadi

Listerner =  Aksi yang akan dilakukan jika event terpanggil.

## Roadmap

* [X] Setup Laravel + Composer
* [X] Setup Auth with `php artisan make:auth`
* [X] Send Email, after user register.
* [X] Send Email, When User Login.
* [X] Insert login history when User Login.

## Step By Step
- `laravel new laravel-workshop`
- `php artisan make:auth`
- Register Event and Listener in App/Providers/EventServiceProvider
- Masukkan event dan listener yang kamu buat di variabel `$listen`
```php
    protected $listen = [
        'App\Events\UserRegisteredEvent' => [
            'App\Listeners\RegisterEmailListener',
        ]
    ];
```
- Kemudian, jalankan command `php artisan event:generate` dan voila, file dibuat secara otomatis.
- lalu, isi listener dengan 
- untuk memanggil event, dapat menggunakan `event(new \App\Events\UserRegisteredEvent($user))` di controller yang ingin dilakukan aksi.


# Note
1. Event untuk Auth built in laravel sudah tersedia.
https://laravel.com/docs/5.4/authentication#events
