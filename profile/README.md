# 💖 SCharity - Transparent Crowdfunding Platform

<div align="center">

![SCharity Banner](https://img.shields.io/badge/SCharity-Cùng_Nhau_Thay_Đổi-F43F5E?style=for-the-badge)
[![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
[![Redux Toolkit](https://img.shields.io/badge/Redux-593D88?style=for-the-badge&logo=redux&logoColor=white)](https://redux-toolkit.js.org/)
[![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![React Query](https://img.shields.io/badge/-React%20Query-FF4154?style=for-the-badge&logo=react%20query&logoColor=white)](https://tanstack.com/query/v3/)

**Nền tảng gây quỹ từ thiện minh bạch và uy tín tại Việt Nam**

[Features](#-features) • [Architecture](#-architecture) • [Quick Start](#-quick-start) • [Tech Stack](#-tech-stack) • [Team](#-team)

</div>

---

## 📖 About

**SCharity** là một nền tảng gây quỹ từ thiện trực tuyến, kết nối giữa các nhà tài trợ (Donor) với các dự án, chiến dịch từ thiện mang ý nghĩa sâu sắc đến cộng đồng. SCharity ra đời với sứ mệnh mang đến sự minh bạch tuyệt đối, tự động hoá quy trình phê duyệt – giải ngân, và tối ưu hoá luồng trải nghiệm đóng góp cho xã hội.

### 🎯 Key Highlights

- **💸 Hỗ trợ linh hoạt** - Quyên góp ẩn danh hoặc công khai, linh hoạt lưu lịch sử đóng góp
- **🔒 Xác thực định danh (eKYC)** - Minh bạch thông tin người tạo dự án và quy trình thiết lập chiến dịch
- **📊 Admin Dashboard System** - Tính năng báo cáo thống kê chuyên sâu về dòng tiền quyên góp
- **📢 Nhật ký dự án** - Chức năng Timeline giúp người tạo báo cáo tiến độ bằng minh chứng hình ảnh/video
- **⚠️ Hệ thống rà soát tự động** - Tiếp nhận "Report" và có công cụ can thiệp khẩn cấp đối với dự án sai lệch
- **🎨 Giao diện tương tác cao** - Được thiết kế theo chuẩn JolyUI với hiệu ứng Glassmorphism hiện đại

---

## ✨ Features

### 💻 Quản trị viên (Admin)
- **Thống kê toàn diện (Dashboard):** Xem tổng quan các dự án, số liệu người dùng và dòng tiền (thu-chi).
- **Phê duyệt chiến dịch:** Xem xét và quyết định Accept/Reject các yêu cầu khởi tạo từ người tạo dự án.
- **Xử lý lệnh giải ngân:** Tiếp nhận, xem xét và cấp phép giao dịch cấp vốn quyên góp.
- **Kiểm duyệt & Chế tài:** Cưỡng chế "Suspend/Unsuspend" các dự án có dấu hiệu vi phạm và tiếp nhận "Report".

### 💼 Người tạo chiến dịch (Campaign Creator)
- **Thiết lập dự án (Create Campaign):** Trình bày câu chuyện, tải lên minh chứng, đặt số tiền mục tiêu và thời hạn.
- **Cập nhật tiến trình:** Tạo các bài viết cập nhật (Update progress) có kèm minh chứng để gửi báo cáo thông qua Timeline tới nhà hảo tâm.
- **Quản lý tài chính:** Tra cứu trực tiếp thống kê (Analytics) từng dự án. Gửi yêu cầu rút tiền (Withdraw Request) khi chạm mốc 50% hoặc 100%.

### 🤝 Nhà tài trợ (Donor) & Khách (Guest)
- **Duyệt dự án:** Khám phá (Browse) và xem chi tiết (View Details) các chiến dịch đang nổi bật.
- **Quyên góp (Donate):** Lựa chọn tuỳ chọn đóng góp Công khai (Public) hoặc Ẩn danh (Anonymous).
- **Lịch sử & Lan tỏa:** Theo dõi lại lịch sử quyên góp (Donation History) cá nhân và gửi lại những lời chúc/động viên (Comments) vào từng dự án.

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    SCHARITY PLATFORM                        │
└─────────────────────────────────────────────────────────────┘

┌──────────────────────┐         ┌──────────────────────────┐
│   Website (FE)       │         │   Backend API (BE)       │
│   (Next.js App)      │◄───────►│   (NodeJS/REST API)      │
│                      │  HTTPS  │                          │
│  • Public Pages      │         │   • Authentication       │
│  • Donor Dashboard   │         │   • Campaign Services    │
│  • Creator Desk      │         │   • Payment Gateway Hook │
│  • Admin Control     │         │   • Admin Services       │
└──────────────────────┘         └──────────────────────────┘
           │                               │
┌──────────▼───────────┐         ┌─────────▼────────────────┐
│      Redux State     │         │       Databases          │
│    (RTK Query &      │         │   (NoSQL / Relational)   │
│     Redux Toolkit)   │         │                          │
└──────────────────────┘         └──────────────────────────┘
```

### Repository Structure

```
SCharity/
├── SCharity_BE/             # Backend API Server
│   ├── src/                 # System services & controllers
│   ├── package.json
│   └── ...
│
└── SCharity_FE/             # Frontend Next.js Application
    ├── app/                 # Next.js App Router (Pages & Layout)
    ├── components/          # Reusable UI & Layout Components
    ├── lib/                 # Core logic, Utilities
    │   └── store/           # Redux Toolkit & RTK Query
    ├── public/              # Static assets
    └── package.json
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- npm hoặc yarn
- Chìa khoá API từ Google OAuth (Cho chứng thực Đăng nhập Google)

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/SCharityFU/SCharity_FE.git
cd SCharity_FE
```

### 2️⃣ Setup Frontend (FE)

```bash
npm install

# Create .env.local file using provided variables
cp .env.example .env.local

# Add your credentials to .env.local
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your_google_client_id.apps.googleusercontent.com
NEXT_PUBLIC_API_URL=http://localhost:5000/api

# Start the dev server
npm run dev
```

Ứng dụng Frontend sẽ khởi động trên `http://localhost:3000`

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: [Next.js](https://nextjs.org/) (App Router, Server Components)
- **UI Library**: [React.js](https://react.dev/)
- **State Management**: [Redux Toolkit](https://redux-toolkit.js.org/) & RTK Query
- **Styling**: [TailwindCSS v3](https://tailwindcss.com/)
- **Design Components**: [Lucide React](https://lucide.dev/), Rainbow Button, Glassmorphism Cards
- **Authentication**: `@react-oauth/google`

### External Services
- **Google OAuth API** - Xác thực người dùng (Đăng nhập)
- **Cổng thanh toán điện tử** - Quản lý giao dịch Quyên góp (VNPay, Stripe,...)

---

## 📱 Supported Actors

👨‍💻 **Admin** | 🤝 **Donor** | 📋 **Campaign Creator** | 🌍 **Guest**

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
