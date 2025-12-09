## 📊 DATABASES CẦN WHITELIST

### 1. PostgreSQL - Configuration Database
- **IP:** `10.10.12.83`
- **Port:** `8201`
- **Database:** `configuration`
- **User:** `postgres`
- **Password:** `Galaxy@1234`
- **Dùng để:** Lưu trữ cấu hình jobs và tasks cho training pipelines

---

### 2. PostgreSQL - Data Warehouse (Data Engineer Team)
- **IP:** `10.10.12.202`
- **Port:** `5432`
- **Database:** `report`
- **User:** `recommendation_team`
- **Password:** `%`cXvznY)-)4SXtT`
- **Views cần truy cập:**
  - `public.ch_view_playing_event_for_analysis`
  - `public.view_all_film_status_for_data_science`
  - `public.mv_view_because_you_watch`
- **Dùng để:** Đọc dữ liệu playing events và metadata phim

---

### 3. MongoDB - Input Database
- **IP:** `10.10.12.83`
- **Port:** `27017`
- **Database:** `user_behavior_db`
- **Collection:** `playing_data`
- **Dùng để:** Đọc raw playing events

---

### 4. MongoDB - Serving Database (Main)
- **IP:** `10.10.12.83`
- **Port:** `8210`
- **Database:** `recommendation`
- **Collection:** `serving_recommendation`
- **Dùng để:** Ghi recommendations để serving vào production

---

### 5. MongoDB - Serving Database Clone (A/B Testing)
- **IP:** `10.10.12.83`
- **Port:** `27018`
- **Database:** `recommendation`
- **Collection:** `serving_recommendation`
- **Username:** `root`
- **Password:** `w9YE2lEq4so36Xytk4Q`
- **Dùng để:** Clone database cho A/B testing

---

### 6. MongoDB - Personalized Items Clustering Database
- **IP:** `10.10.12.83`
- **Port:** `27018`
- **Database:** `clustering_personalized_recommendation`
- **Collections:** `serving_recommendation`, `items_clusters`
- **Dùng để:** Lưu trữ clustering recommendations

---

### 7. PostgreSQL - Configuration DB (Alternative)
- **IP:** `10.10.23.172`
- **Port:** `5432`
- **Database:** `configuration`
- **User:** `postgres`
- **Password:** `postgres`
- **Dùng để:** Backup/alternative configuration database

---

## 🔄 MESSAGE QUEUE SERVICES CẦN WHITELIST

### 8. Kafka
- **IP:** `10.10.24.72`
- **Port:** `9092`
- **Dùng để:** Event streaming cho online serving

---

### 9. RabbitMQ
- **IP:** `10.10.24.71`
- **Port:** `5672`
- **Username:** `bedac_recsys`
- **Password:** `7Jmtjbf754jGGvbnqsoe`
- **Exchange:** `recsys`
- **Routing Keys:** `recsys.because_you_watched.update`, `recsys.recommended_for_you.update`
- **Dùng để:** Publish recommendations updates

---

## 🚀 OTHER SERVICES CẦN WHITELIST

### 10. MLflow Tracking Server
- **IP:** `10.10.12.83`
- **Port:** `5000`
- **Dùng để:** ML experiment tracking và model registry

---

### 11. Vector Database (Qdrant)
- **HTTP Port:** `6333`
- **gRPC Port:** `6334`
- **Dùng để:** Lưu trữ embeddings cho similarity search

---

## 🌐 EXTERNAL SERVICES CẦN ACCESS

### 12. Jira API
- **URL:** `https://jira-glxplay.atlassian.net`
- **Project Key:** `CMM`
- **Email:** `daclth@galaxy.com.vn`
- **API Token:** `QPEQWpDeiRSDpgIfaYJj5FAF`
- **Dùng để:** Tạo issues để approve training results

---

### 13. Feature Store
- **Repository:** `https://bitbucket.org/fimplus/recsys-feature-store`
- **Dùng để:** Centralized feature management

---

## 🔒 NETWORK ACCESS CẦN WHITELIST

### IP Ranges cần truy cập:
- **10.10.12.x:**
  - `10.10.12.83` - MongoDB, PostgreSQL Config, MLflow
  - `10.10.12.202` - Data Warehouse (PostgreSQL)
- **10.10.24.x:**
  - `10.10.24.72` - Kafka
  - `10.10.24.71` - RabbitMQ
- **10.10.23.x:**
  - `10.10.23.172` - PostgreSQL Config (alternative)

### Ports cần mở:
- PostgreSQL: `8201`, `5432`
- MongoDB: `27017`, `8210`, `27018`
- MLflow: `5000`
- Kafka: `9092`
- RabbitMQ: `5672`
- Qdrant: `6333`, `6334`

---

## 🔑 CREDENTIALS CẦN XÁC NHẬN

1. **Database Passwords:**
   - PostgreSQL Config DB: `Galaxy@1234`
   - Data Warehouse: `%`cXvznY)-)4SXtT`
   - MongoDB Clone: `w9YE2lEq4so36Xytk4Q`
   - PostgreSQL Alt: `postgres`

2. **API Tokens:**
   - Jira API token: `QPEQWpDeiRSDpgIfaYJj5FAF`
   - AWS S3 credentials (nếu cần)
   - Access Token cho Galaxy Play API (JWT token)
   - Sentry DSN (nếu cần)

---

## 🎯 MỤC ĐÍCH SỬ DỤNG

- Test và phát triển hệ thống Recommendation System
- Fix bugs và debug issues
- Chạy training pipelines với dữ liệu thực tế
- Test serving recommendations
- Validate data flow và integration

**Phạm vi truy cập:**
- **Read-only** cho Data Warehouse
- **Read/Write** cho Configuration DB và Serving DB
- **Read** cho Input DB

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
| PostgreSQL Alt Config | 10.10.23.172 | 5432 | TCP |


---

## ✅ TESTING CHECKLIST

Sau khi được cấp quyền, tôi sẽ test:
- [ ] Kết nối đến PostgreSQL Config DB
- [ ] Kết nối đến Data Warehouse
- [ ] Kết nối đến MongoDB (tất cả instances)
- [ ] Kết nối đến Kafka
- [ ] Kết nối đến RabbitMQ
- [ ] Kết nối đến MLflow
- [ ] Kết nối đến Vector DB (Qdrant)
- [ ] Đọc dữ liệu từ Data Warehouse
- [ ] Đọc dữ liệu từ MongoDB Input DB
- [ ] Ghi recommendations vào Serving DB
- [ ] Test Jira API integration
- [ ] Chạy training pipeline end-to-end
