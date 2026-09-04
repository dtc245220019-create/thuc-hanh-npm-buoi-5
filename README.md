# Nginx Proxy Manager & Docker Reverse Proxy Lab

Mô hình Reverse Proxy sử dụng Nginx Proxy Manager (NPM) điều hướng tên miền ảo cho Static Site và WordPress trong môi trường Docker Ubuntu.

## Cấu trúc mạng & Cổng (Ports)
- **NPM Admin Dashboard**: `http://127.0.0.1:81`
- **Reverse Proxy Entry Port**: `8081`
- **Docker Network**: `npm_network`

## Danh sách tên miền ảo (Virtual Domains)
- `http://static.local:8081` -> Container `static-site:80`
- `http://wordpress.local:8081` -> Container `wordpress:80`

## Hướng dẫn triển khai
1. Tạo Docker Network:
   \`\`\`bash
   docker network create npm_network
   \`\`\`
2. Khởi chạy Nginx Proxy Manager:
   \`\`\`bash
   docker compose up -d
   \`\`\`
3. Thêm cấu hình trong `/etc/hosts`:
   \`\`\`text
   127.0.0.1 static.local wordpress.local
   \`\`\`
# thuc-hanh-npm-buoi-5
