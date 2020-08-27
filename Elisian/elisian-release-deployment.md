---
title: "Release and Deployment Elisian"
date: "2019-11-27"
document type: "6"
author: "Shindy Farrahdiba"
summary: "Dokumen ini menjelaskan langkah-langkah dalam melakukan proses release dan deploy"
---

# Schedule and Step 
## Release Preparation
1. Buat *branch release*/YYYYMMDD dari *branch develop*
2. *Finish branch* "*release*"
3. Git push develop
4. Git push master
5. Buat *new release* di Github
    - Pilih sebuah *existing tag*, atau buat *tag* baru di *publish*
    - *Add release* (*Title Elisian Release* YYYYMMDD)
    - *Add list* dari semua *accepted stories* dalam deskripsi
    - *Publish Release*
6. Buat *Release Story* di Pivotal dengan judul *Elisian Release* YYYYMMDD
7. *Update* *Release Story description* dengan *Release Note* (Title ‘’’Elisian Release YYYYMMDD’’’) dan tambahkan *list* dari semua *accepted stories*
8. ‘’’Finish’’’ *release story* di Pivotal
9. Kirim *email* ke Stakeholders

## Deployment
1. Pergi ke *root* dari Elisian *project* di *server* `cd /sepulsa/www/elisian`
2. `git pull` untuk melakukan *pull* *commit* terbaru.
3. `composer dump-autoload && php artisan clear-compiled && php artisan auth:clear-resets && php artisan cache:clear && php artisan config:clear && php artisan route:clear && php artisan view:clear` untuk *clean project cache*.