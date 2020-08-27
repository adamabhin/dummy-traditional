---
title: "Developer Onboarding Elisian"
date: "2019-11-27"
document type: "6"
author: "Shindy Farrahdiba"
summary: "Dokumen ini menjelaskan tools dan local machine setup bagi developer baru"
---

# Prequisites
| Nama | Deskripsi |
| -----| ----------|
| Programming Language | PHP CLI >= 7.1.x |
| Composer Package Manager | https://getcomposer.org/download/ |
| Database | MySQL (>= 5.5.x) |
| | PostgreSQL (>= 9.5.5) |

# Tools
Beberapa tools yang disarankan untuk Development adalah sebagai berikut:
1. MAMP
2. Visual Code Studio
3. Sublime Text

# Local Machine Setup
1. Download *project* ini dari github *repository* "[https://github.com/sepulsa/elisian](https://github.com/sepulsa/elisian)".
2. Buat database dengan nama `elisian` di dalam *local environment*-mu.
3. `cp .env.example .env` dan atur *local configurations*.
4. `composer install` untuk *install dependency packages*.
5. `php artisan migrate --seed` untuk *migrate* dan *seeding* si *database*.
6. `sudo chmod -R 0777 storage && sudo chmod -R 0777 public/file` untuk memastikan *storage directories* punya *permissions* yang tepat.
7. Atur *supervisor configuration*-mu seperti berikut:

        [program:elisian-worker]
        
        process_name=%(program_name)s_%(process_num)02d
        
        command=php /home/forge/example.com/artisan queue:work --sleep=3 --tries=3 --daemon

        autostart=true
        
        autorestart=true
        
        user=forge
        
        numprocs=3
        
        redirect_stderr=true
        
        stdout_logfile=/home/forge/example.com/storage/logs/supervisor.l

8. `composer dump-autoload && php artisan clear-compiled && php artisan auth:clear-resets && php artisan cache:clear && php artisan config:clear && php artisan route:clear && php artisan view:clear` untuk membersihkan *project cache*.