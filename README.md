# Session 12 - Bài 1: Quy trình CI đa phiên bản JDK (Matrix Strategy)

## 📌 Mô tả
Dự án Spring Boot Gradle với cấu hình GitHub Actions Matrix Strategy để chạy kiểm thử tự động song song trên nhiều phiên bản JDK (JDK 17 và JDK 21), kết hợp với Gradle Dependency Caching.

## 🚀 Cấu hình GitHub Actions Matrix
- Tệp kịch bản: `.github/workflows/ci-matrix.yml`
- Kích hoạt: Sự kiện `push` vào nhánh `main`
- Job: `test-matrix`
- Chiến lược ma trận:
  - `java-version: ['17', '21']`
- Các bước thực thi:
  - `actions/checkout@v5`: Checkout mã nguồn dự án
  - `actions/setup-java@v5`: Thiết lập JDK tương ứng từ ma trận với `distribution: 'temurin'` và `cache: 'gradle'`
  - Cấp quyền thực thi: `chmod +x gradlew`
  - Thực thi kiểm thử: `./gradlew test`

## 📁 Cấu trúc thư mục
```
├── .github/
│   └── workflows/
│       └── ci-matrix.yml
├── gradle/
│   └── wrapper/
├── src/
│   ├── main/java/...
│   └── test/java/...
├── homework/
│   └── session_12/
│       └── ex1/
│           ├── ci-matrix.yml
│           └── report.md
├── build.gradle
├── settings.gradle
├── gradlew
├── gradlew.bat
└── README.md
```
