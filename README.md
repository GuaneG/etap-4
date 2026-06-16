# Etap 4 — ETL'i Containerize Et (Docker)

> Yol haritamın 4. etabı (EPAM içinde). Docker'ı [EPAM Campus — Cloud & DevOps](https://campus.epam.com/en/training/5329) programının "Containerization: Docker Practice" modülünden öğrenip, Etap 3'teki ETL projesini Docker'a taşıyorum. Tek komutla hem veritabanı hem ETL ayağa kalkıyor.

`docker compose up` deyince önce PostgreSQL kalkıyor, sonra ETL scripti çalışıp veriyi yazıyor. Veri, volume sayesinde `down`/`up` sonrası korunuyor.

## Mimari
```
docker-compose.yml
├── postgres   (resmi image + volume → veri kalıcı)
└── etl        (Dockerfile'dan build → Etap 3 scripti)
```

## Kullanılan araçlar
- **Docker** + **docker compose**
- Resmi `postgres` image'i
- Etap 3'ün Python ETL scripti

## Kaynaklar
- **Ana kurs:** EPAM Cloud & DevOps — "Containerization: Docker Practice" modülü (Etap 2 ile aynı program)
- **İstersen destek (opsiyonel):** [Docker Get Started](https://docs.docker.com/get-started/) · [freeCodeCamp Docker Tutorial (video)](https://www.youtube.com/watch?v=fqMOX6JJhGo)

## Çalıştırma
```bash
docker compose up        # her şeyi ayağa kaldır
docker compose logs etl  # ETL loglarını gör
docker compose down      # durdur (veri volume'da kalır)
```

## Notlar
<!-- TODO: servis adıyla DB host, volume, image vs container hakkında notlar -->

## ✅ Etap 4 Bitiş Kontrol Listesi
- [ ] Image ve container farkını açıklayabiliyorum
- [ ] Kendi Python uygulamam için Dockerfile yazabiliyorum
- [ ] docker compose ile birbirine bağlı iki servisi ayağa kaldırabiliyorum
- [ ] Volume'un veriyi neden kaybettirmediğini açıklayabiliyorum
- [ ] Çalışmayan bir container'ın loglarından (`docker logs`) sorunu bulabiliyorum
