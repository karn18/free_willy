# Free Willy

เป็น template ของ Docker ในการสร้างแวดล้อมในการพัฒนาโปรแกรมด้วย Ruby On Rails พร้อมกับฐานข้อมูล PostgreSQL

## Current Stack:
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
- สร้างฐานข้อมูล

## References
- [https://evilmartians.com/chronicles/ruby-on-whales-docker-for-ruby-rails-development](https://evilmartians.com/chronicles/ruby-on-whales-docker-for-ruby-rails-development)
- [https://github.com/evilmartians/terraforming-rails/tree/master/examples/dockerdev](https://github.com/evilmartians/terraforming-rails/tree/master/examples/dockerdev)