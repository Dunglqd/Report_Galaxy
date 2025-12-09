## 📊 DATABASE ACCESS

### 1. PostgreSQL - Configuration Database
- **IP:** `10.10.12.83`
- **Port:** `8201` (hoặc `5432`)
- **Database:** `configuration`
- **User:** `postgres`
- **Password:** `Galaxy@1234`
- **Purpose:** Lưu trữ cấu hình jobs và tasks cho training pipelines
- **Tables/Views:** `view_task_detail`

---

### 2. PostgreSQL - Data Warehouse (Data Engineer Team)
- **IP:** `10.10.12.202`
- **Port:** `5432`
- **Database:** `report`
- **User:** `recommendation_team`
- **Password:** `%`cXvznY)-)4SXtT`
- **Purpose:** Đọc dữ liệu playing events và metadata phim
- **Views cần truy cập:**
  - `public.ch_view_playing_event_for_analysis`
  - `public.view_all_film_status_for_data_science`
  - `public.mv_view_because_you_watch`

---

### 3. MongoDB - Input Database (User Behavior)
- **IP:** `10.10.12.83`
- **Port:** `27017`
- **Database:** `user_behavior_db`
- **Collection:** `playing_data`
- **Username:** (empty)
- **Password:** (empty)
- **Purpose:** Đọc raw playing events từ MongoDB

---

### 4. MongoDB - Serving Database (Main)
- **IP:** `10.10.12.83`
- **Port:** `8210`
- **Database:** `recommendation`
- **Collection:** `serving_recommendation`
- **Username:** (empty)
- **Password:** (empty)
- **Purpose:** Ghi recommendations để serving vào production

---

### 5. MongoDB - Serving Database Clone (A/B Testing)
- **IP:** `10.10.12.83`
- **Port:** `27018`
- **Database:** `recommendation`
- **Collection:** `serving_recommendation`
- **Username:** `root`
- **Password:** `w9YE2lEq4so36Xytk4Q`
- **Purpose:** Clone database cho A/B testing

---

### 6. MongoDB - Personalized Items Clustering Database
- **IP:** `10.10.12.83`
- **Port:** `27018`
- **Database:** `clustering_personalized_recommendation`
- **Collections:** 
  - `serving_recommendation`
  - `items_clusters`
- **Purpose:** Lưu trữ clustering recommendations

---

### 7. PostgreSQL - Configuration DB (Alternative/Coordinator)
- **IP:** `10.10.23.172`
- **Port:** `5432`
- **Database:** `configuration`
- **User:** `postgres`
- **Password:** `postgres`
- **Purpose:** Backup/alternative configuration database

---

## 🔄 MESSAGE QUEUE SERVICES

### 8. Kafka
- **IP:** `10.10.24.72`
- **Port:** `9092`
- **Purpose:** Event streaming cho online serving
- **Protocol:** Kafka protocol

---

### 9. RabbitMQ
- **IP:** `10.10.24.71`
- **Port:** `5672`
- **Username:** `bedac_recsys`
- **Password:** `7Jmtjbf754jGGvbnqsoe`
- **Exchange:** `recsys`
- **Exchange Type:** `topic`
- **Virtual Host:** `/`
- **Routing Keys:**
  - `recsys.because_you_watched.update`
  - `recsys.recommended_for_you.update`
- **Purpose:** Publish recommendations updates

---

## 🚀 OTHER SERVICES

### 10. MLflow Tracking Server
- **IP:** `10.10.12.83`
- **Port:** `5000`
- **Purpose:** ML experiment tracking và model registry
- **Protocol:** HTTP

---

### 11. Vector Database (Qdrant)
- **Host:** `vector-db` (trong Docker network) hoặc IP tương ứng
- **HTTP Port:** `6333`
- **gRPC Port:** `6334`
- **Purpose:** Lưu trữ embeddings cho similarity search

---

### 12. S3/MinIO Storage
- **API Port:** `9000`
- **Console Port:** `9001`
- **Purpose:** Lưu trữ MLflow artifacts và model files
- **Note:** Endpoint được cấu hình qua environment variables

---

## 🌐 EXTERNAL SERVICES

### 13. Jira API
- **URL:** `https://jira-glxplay.atlassian.net`
- **Project Key:** `CMM`
- **Email:** `daclth@galaxy.com.vn`
- **API Token:** `QPEQWpDeiRSDpgIfaYJj5FAF`
- **Purpose:** Tạo issues để approve training results
- **Note:** Cần user có permission để create issues

---

### 14. Feature Store
- **Repository:** `https://bitbucket.org/fimplus/recsys-feature-store`
- **Purpose:** Centralized feature management
- **Note:** Đây là repository riêng, cần quyền truy cập riêng

---

## 🔒 NETWORK ACCESS REQUIREMENTS

Cần quyền truy cập network đến các IP ranges sau:

### Main Servers (10.10.12.x)
- `10.10.12.83` - MongoDB, PostgreSQL Config, MLflow
- `10.10.12.202` - Data Warehouse (PostgreSQL)

### Message Queue Servers (10.10.24.x)
- `10.10.24.72` - Kafka
- `10.10.24.71` - RabbitMQ

### Alternative Config Server (10.10.23.x)
- `10.10.23.172` - PostgreSQL Config (alternative)

---

## 🔑 CREDENTIALS NEEDED

Xin vui lòng cung cấp hoặc xác nhận:

1. **Database Passwords/Credentials:**
   - PostgreSQL Config DB password (nếu đã thay đổi)
   - MongoDB passwords (nếu có thay đổi)
   - Data Warehouse credentials (nếu đã thay đổi)

2. **API Tokens:**
   - Jira API token (nếu cần tạo mới)
   - AWS S3 credentials (nếu cần)
   - Sentry DSN (nếu cần)

3. **Network Access:**
   - VPN access hoặc whitelist IP của tôi
   - Firewall rules để mở các ports cần thiết

---

## 🎯 TESTING PURPOSE

**Mục đích sử dụng:**
- Test và phát triển hệ thống Recommendation System
- Chạy training pipelines với dữ liệu thực tế
- Test serving recommendations
- Validate data flow và integration
- Debug và fix issues
- Performance testing

**Phạm vi truy cập:**
- **Read-only** cho Data Warehouse (chỉ đọc dữ liệu)
- **Read/Write** cho Configuration DB (tạo jobs, tasks)
- **Read/Write** cho Serving DB (ghi recommendations)
- **Read** cho Input DB (đọc playing events)

---

## 📋 PORTS SUMMARY

| Service | IP | Port | Protocol |
|---------|-----|------|----------|
| PostgreSQL Config | 10.10.12.83 | 8201 | TCP |
| PostgreSQL Data Warehouse | 10.10.12.202 | 5432 | TCP |
| MongoDB Input | 10.10.12.83 | 27017 | TCP |
| MongoDB Serving | 10.10.12.83 | 8210 | TCP |
| MongoDB Clone | 10.10.12.83 | 27018 | TCP |
| Kafka | 10.10.24.72 | 9092 | TCP |
| RabbitMQ | 10.10.24.71 | 5672 | TCP |
| MLflow | 10.10.12.83 | 5000 | HTTP |
| Qdrant HTTP | vector-db | 6333 | HTTP |
| Qdrant gRPC | vector-db | 6334 | gRPC |
| S3 API | - | 9000 | HTTP |
| S3 Console | - | 9001 | HTTP |

---

## ✅ TESTING CHECKLIST

Sau khi được cấp quyền, tôi sẽ test:

- [ ] Kết nối đến PostgreSQL Config DB
- [ ] Kết nối đến Data Warehouse
- [ ] Kết nối đến MongoDB (tất cả instances)
- [ ] Kết nối đến Kafka
- [ ] Kết nối đến RabbitMQ
- [ ] Kết nối đến MLflow
- [ ] Đọc dữ liệu từ Data Warehouse
- [ ] Ghi recommendations vào Serving DB
- [ ] Chạy training pipeline end-to-end
