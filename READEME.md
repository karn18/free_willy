# Free Willy

เป็น template ของ Docker ในการสร้างแวดล้อมในการพัฒนาโปรแกรมด้วย Ruby On Rails พร้อมกับฐานข้อมูล PostgreSQL

## Current Stack

- Ruby 2.6.5
- Postgresql 12.3
- NodeJS 12 and Yarn 1.22.4
- Bundler 2.1.4

> สามารแก้ไขเวอร์ชันที่จะใช้งานได้ในไฟล์ docker-compose.yml

## Dockerfile.app

## Dockerfile.postgres

- สร้าง image ของ postgresql ที่รองรับ locale TH

## วิธีการใช้งาน

- ติดตั้ง dependencies ของ node

```bash
$ docker-compose run runner yarn install
```

- ติดตั้ง dependencies ของ rails

```bash
$ docker-compose run runner bundle install
```

- สร้างฐานข้อมูล

```bash
$ docker-compose run postgres psql -U postgres -W -h postgres -c "create database DB_NAME LC_COLLATE 'th_TH.UTF-8' LC_CTYPE 'th_TH.UTF-8' template template0"
```

> เปลี่ยน DB_NAME ให้ตรงกับชื่อที่เราใช้งานซึ่งสามารถดูได้ใน `config/database.yml`

- Migrate Database

```bash
$ docker-compose run runner rails db:migrate
```

- Run Rails Server

```bash
$ docker-compose run rails
```

- ตอนนี้เราสามารถจะเข้าถึงเว็บแอพของเราได้ผ่าน [http://localhost:3000](http://localhost:3000)

## References

- [https://evilmartians.com/chronicles/ruby-on-whales-docker-for-ruby-rails-development](https://evilmartians.com/chronicles/ruby-on-whales-docker-for-ruby-rails-development)
- [https://github.com/evilmartians/terraforming-rails/tree/master/examples/dockerdev](https://github.com/evilmartians/terraforming-rails/tree/master/examples/dockerdev)
