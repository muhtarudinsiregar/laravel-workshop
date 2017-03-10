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
1. `laravel new laravel-workshop`
2. `php artisan make:auth`
3. Register Event and Listener in App/Providers/EventServiceProvider
4. Masukkan event dan listener yang kamu buat di variabel `$listen`
```php
    protected $listen = [
        'App\Events\UserRegisteredEvent' => [
            'App\Listeners\RegisterEmailListener',
        ]
    ];
```
5. Kemudian, jalankan command `php artisan event:generate` dan voila, file dibuat secara otomatis.
6. lalu, isi listener dengan 
7. untuk memanggil event, dapat menggunakan `event(new \App\Events\UserRegisteredEvent($user))` di controller yang ingin dilakukan aksi.


# Note
1. Event untuk Auth built in laravel sudah tersedia.
https://laravel.com/docs/5.4/authentication#events
