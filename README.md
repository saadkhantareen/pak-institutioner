# 🎓 NUCAP - National University Admission Platform

<div align="center">

![NUCAP Logo](https://img.shields.io/badge/NUCAP-University%20Admission%20Platform-blue?style=for-the-badge)

**Empowering 1M+ Pakistani Students to Never Miss a University Deadline**

[![GitHub](https://img.shields.io/badge/GitHub-saadkhantareen%2Fpak--institutioner-181717?style=flat&logo=github)](https://github.com/saadkhantareen/pak-institutioner)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Next.js](https://img.shields.io/badge/Next.js-15.5-black?logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?logo=typescript)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue?logo=postgresql)](https://www.postgresql.org/)

[🚀 Live Demo](#) | [📖 Documentation](#documentation) | [🐛 Report Bug](https://github.com/saadkhantareen/pak-institutioner/issues) | [✨ Request Feature](https://github.com/saadkhantareen/pak-institutioner/issues)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Getting Started](#-getting-started)
- [API Documentation](#-api-documentation)
- [Database Schema](#-database-schema)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 Overview

**NUCAP** (National University Admission Platform) is a comprehensive web application designed to solve the critical problem of students missing university admission deadlines in Pakistan. Every year, thousands of talented students lose opportunities because admission information is scattered across multiple university websites, frequently changes, and is difficult to track.

### Key Statistics
- 🎓 **Target Users**: 1M+ Intermediate (12th grade) students
- 🏫 **Universities Covered**: NUST, FAST, COMSATS, Punjab University (expandable)
- ⏰ **Automated Tracking**: Real-time deadline monitoring and alerts
- 📊 **Smart Matching**: AI-powered university recommendations based on academic profile

---

## 💡 Problem Statement

### The Challenge

Pakistani students face several challenges during university admissions:

1. **Scattered Information** 📚
   - Each university has its own website with different layouts
   - Admission criteria changes frequently
   - Merit lists published at different times

2. **Missed Deadlines** ⏰
   - No centralized platform for deadline tracking
   - Manual checking of multiple websites is time-consuming
   - Last-minute announcements go unnoticed

3. **Uncertainty** ❓
   - Students don't know their admission chances
   - Comparing merit across universities is difficult
   - No guidance on which universities to apply to

### Our Solution

NUCAP solves these problems by:

✅ **Centralizing** all university information in one place  
✅ **Automating** deadline tracking and notifications  
✅ **Calculating** merit and matching students with universities  
✅ **Providing** real-time updates and announcements  
✅ **Simplifying** the entire admission process  

---

## ✨ Features

### For Students

#### 🎯 Academic Profile Management
- Create comprehensive academic profile
- Store Matric and Inter marks
- Add test scores (NUST, FAST, NTS)
- Set preferences (cities, fields, budget)

#### 📊 Merit Calculator
- Calculate merit for multiple universities instantly
- University-specific formulas (NUST, FAST, COMSATS, Punjab)
- Real-time percentage calculation
- Estimated vs. required merit comparison

#### 🎓 Smart University Matching
- AI-powered recommendations based on profile
- Match score algorithm (0-100)
- Admission chances (High/Good/Medium/Low)
- Merit gap analysis
- Department-wise breakdown

#### ⏰ Deadline Tracking
- Upcoming deadlines dashboard
- Countdown timers
- Multi-university tracking
- Important date reminders

#### 📰 Real-Time Updates
- Latest announcements from universities
- Merit list publications
- Deadline extensions
- Important notices

#### 🔍 University Explorer
- Browse all universities
- Filter by city, test type, field
- Department details
- Historical merit data
- Direct application links

### For Administrators

#### 🛠️ Admin Dashboard
- System statistics overview
- User analytics
- Scraping activity monitoring
- Manual data entry forms

#### 🤖 Web Scraping Management
- Automated data collection from university websites
- Custom scrapers for each university
- Scraping logs and error tracking
- Manual trigger for on-demand updates

#### 📝 Content Management
- Add/edit university information
- Update admission timelines
- Publish announcements
- Manage merit lists

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 15.5 (App Router)
- **Language**: TypeScript 5.0
- **Styling**: Tailwind CSS 4.0
- **UI Components**: Shadcn/ui
- **Icons**: Lucide React
- **Forms**: React Hook Form + Zod validation

### Backend
- **Runtime**: Node.js 22
- **API**: Next.js API Routes
- **Authentication**: Clerk
- **Database**: PostgreSQL 16
- **ORM**: Prisma 6.17

### Infrastructure
- **Hosting**: Vercel
- **Database Hosting**: Vercel Postgres / Supabase / Neon
- **Cron Jobs**: Vercel Cron
- **Web Scraping**: Jina AI API + Cheerio

### Development Tools
- **Package Manager**: npm
- **Linting**: ESLint
- **Type Checking**: TypeScript
- **Database GUI**: Prisma Studio

---

## 🏗️ Architecture

### System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        CLIENT (Browser)                         │
│                     Next.js 15 Frontend                         │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐       │
│  │  Landing │  │Dashboard │  │Universities│ │ Profile  │       │
│  │   Page   │  │          │  │  Explorer  │ │ Creation │       │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘       │
└────────────────────────┬────────────────────────────────────────┘
                         │ HTTP/HTTPS
                         ▼
┌─────────────────────────────────────────────────────────────────┐
│                    API LAYER (Next.js)                          │
│  ┌────────────────┐  ┌────────────────┐  ┌────────────────┐   │
│  │   Student API  │  │Universities API│  │   Admin API    │   │
│  │  - Profile     │  │  - List        │  │  - Manage Data │   │
│  │  - Merit Calc  │  │  - Details     │  │  - Scraping    │   │
│  │  - Matches     │  │  - Filter      │  │  - Analytics   │   │
│  └────────────────┘  └────────────────┘  └────────────────┘   │
└────────┬──────────────────┬──────────────────┬──────────────────┘
         │                  │                  │
         ▼                  ▼                  ▼
┌────────────────┐  ┌────────────────┐  ┌────────────────┐
│ Authentication │  │    Database    │  │  Web Scraping  │
│     (Clerk)    │  │  (PostgreSQL)  │  │   (Jina AI)    │
│                │  │                │  │                │
│ - User Mgmt    │  │ - Users        │  │ - NUST         │
│ - Sessions     │  │ - Universities │  │ - FAST         │
│ - Protected    │  │ - Departments  │  │ - COMSATS      │
│   Routes       │  │ - Merit Lists  │  │ - Punjab       │
└────────────────┘  └────────────────┘  └────────────────┘
```

### Data Flow

```
Student Creates Profile
         │
         ├─> Save to Database (PostgreSQL)
         │
         ├─> Calculate Merit (All Universities)
         │
         ├─> Generate Matches (Algorithm)
         │
         └─> Display Results (Dashboard)

Automated Scraping (Every 12 hours)
         │
         ├─> Jina AI fetches university websites
         │
         ├─> Custom scrapers extract data
         │
         ├─> Parse deadlines, merit lists, announcements
         │
         ├─> Save to database
         │
         └─> Students see updated information
```

### Merit Calculation Algorithm

```typescript
For each university:
  Student Merit = (Matric% × W1) + (Inter% × W2) + (Test Score × W3)
  
  Where weights differ by university:
  
  NUST:    W1=10%, W2=15%, W3=75% (Test out of 200)
  FAST:    W1=10%, W2=40%, W3=50% (Test out of 100)
  COMSATS: W1=15%, W2=35%, W3=50% (Test out of 100)
  Punjab:  W1=20%, W2=50%, W3=30% (Test out of 100)
```

### Matching Algorithm

```typescript
Match Score (0-100) = Merit Compatibility (50%) 
                    + Location Preference (25%) 
                    + Field Preference (25%)

Admission Chance:
  - Merit Gap ≥ 5%:  HIGH
  - Merit Gap ≥ 0%:  GOOD
  - Merit Gap ≥ -3%: MEDIUM
  - Merit Gap < -3%: LOW
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ installed
- PostgreSQL 16+ installed (or cloud database)
- Clerk account for authentication
- Jina AI API key

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/saadkhantareen/pak-institutioner.git
   cd pak-institutioner/nucap
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   
   Create `.env.local` file:
   ```env
   # Clerk Authentication
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   CLERK_SECRET_KEY=your_clerk_secret_key
   
   # Database
   DATABASE_URL="postgresql://user:password@localhost:5432/nucap?schema=public"
   
   # Jina AI
   JINA_API_KEY=your_jina_api_key
   
   # App
   NEXT_PUBLIC_APP_URL=http://localhost:3000
   CRON_SECRET=your-secret-key
   NODE_ENV=development
   ```

4. **Set up database**
   ```bash
   npx prisma generate
   npx prisma migrate dev
   npx prisma db seed
   ```

5. **Run development server**
   ```bash
   npm run dev
   ```

6. **Open application**
   ```
   http://localhost:3000
   ```

### Quick Start Commands

```bash
# Development
npm run dev              # Start dev server
npm run build            # Build for production
npm run start            # Start production server

# Database
npm run db:generate      # Generate Prisma Client
npm run db:migrate       # Run migrations
npm run db:seed          # Seed database
npm run db:studio        # Open Prisma Studio

# Testing
npm run lint             # Run ESLint
npx tsx scripts/test-scraper.ts NUST  # Test scraper
```

📖 **For detailed setup instructions**, see [SETUP.md](./SETUP.md)  
🚀 **For quick deployment**, see [QUICKSTART.md](./QUICKSTART.md)

---

## 📚 API Documentation

### Student Endpoints

#### Create Profile
```http
POST /api/student/profile
Content-Type: application/json

{
  "matricTotalMarks": 1100,
  "matricObtainedMarks": 950,
  "matricBoard": "Federal",
  "matricYear": 2022,
  "interTotalMarks": 1100,
  "interObtainedMarks": 900,
  "interBoard": "Federal",
  "interGroup": "Pre-Eng",
  "interYear": 2024,
  "nustTestScore": 140,
  "fastTestScore": 75,
  "preferredCities": ["Islamabad", "Lahore"],
  "preferredFields": ["Computer Science", "Engineering"]
}
```

#### Calculate Merit
```http
POST /api/student/calculate-merit
Content-Type: application/json

{
  "matricPercentage": 86.4,
  "interPercentage": 81.8,
  "testScores": {
    "NUST": 140,
    "FAST": 75
  }
}
```

#### Generate Matches
```http
POST /api/student/generate-matches
```

### University Endpoints

#### List Universities
```http
GET /api/universities
GET /api/universities?city=Islamabad
GET /api/universities?testType=NUST
GET /api/universities?category=Engineering
```

#### Get University Details
```http
GET /api/universities/{id}
```

### Admin Endpoints

#### Trigger Scraping
```http
POST /api/cron/scrape-universities
Authorization: Bearer {CRON_SECRET}
```

#### Add Deadline
```http
POST /api/admin/add-deadline
Content-Type: application/json

{
  "universityId": "...",
  "year": 2025,
  "cycle": "Fall 2025",
  "applicationDeadline": "2025-03-15",
  "testDate": "2025-04-20"
}
```

---

## 🗄️ Database Schema

### Core Models

- **User**: Authentication and basic info
- **StudentProfile**: Academic credentials and preferences
- **University**: University information
- **Department**: Program details
- **MeritList**: Historical merit data
- **AdmissionTimeline**: Deadline tracking
- **UniversityUpdate**: News and announcements
- **StudentMatch**: University recommendations
- **ScrapingLog**: Scraping activity logs

### Entity Relationship Diagram

```
User (1) ──────────────> (1) StudentProfile
                               │
                               │ (1)
                               ▼
                          StudentMatch (N)
                               │
        ┌──────────────────────┴──────────────────────┐
        │                                             │
        │ (1)                                    (1)  │
        ▼                                             ▼
   University (1) ─────────────────────> (N) Department
        │                                             │
        ├──────> (N) MeritList                       │
        ├──────> (N) AdmissionTimeline               │
        ├──────> (N) UniversityUpdate                │
        └──────> (N) ScrapingLog                     │
                                                      │
                              ┌───────────────────────┘
                              │
                              ▼
                         MeritList (N)
```

📖 **For complete schema details**, see [prisma/schema.prisma](./prisma/schema.prisma)

---

## 🚢 Deployment

### Deploy to Vercel (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Ready for deployment"
   git push origin main
   ```

2. **Connect to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Import repository
   - Configure environment variables
   - Deploy

3. **Set up Database**
   - Use Vercel Postgres, Supabase, or Neon
   - Run migrations: `npx prisma migrate deploy`
   - Seed data: `npx prisma db seed`

4. **Configure Clerk**
   - Update allowed domains in Clerk dashboard
   - Set production redirect URLs

📖 **For detailed deployment guide**, see [DEPLOYMENT.md](./DEPLOYMENT.md)

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Ways to Contribute

- 🐛 **Report Bugs**: [Open an issue](https://github.com/saadkhantareen/pak-institutioner/issues)
- ✨ **Request Features**: [Suggest enhancements](https://github.com/saadkhantareen/pak-institutioner/issues)
- 💻 **Submit Code**: [Create a pull request](https://github.com/saadkhantareen/pak-institutioner/pulls)
- 📖 **Improve Docs**: Help us improve documentation
- 🎨 **Design**: Contribute UI/UX improvements

### Development Process

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test thoroughly
5. Commit (`git commit -m 'Add amazing feature'`)
6. Push (`git push origin feature/amazing-feature`)
7. Open a Pull Request

### Code Style

- Use TypeScript for all new code
- Follow existing code patterns
- Add comments for complex logic
- Write meaningful commit messages
- Update documentation as needed

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Saad Khan Tareen**

- GitHub: [@saadkhantareen](https://github.com/saadkhantareen)
- Project: [pak-institutioner](https://github.com/saadkhantareen/pak-institutioner)

---

## 🙏 Acknowledgments

- **Jina AI** for web scraping capabilities
- **Clerk** for authentication services
- **Vercel** for hosting platform
- **Shadcn/ui** for beautiful UI components
- All contributors and supporters

---

## 📞 Contact & Support

- **GitHub Issues**: [Report a problem](https://github.com/saadkhantareen/pak-institutioner/issues)
- **Discussions**: [Ask questions](https://github.com/saadkhantareen/pak-institutioner/discussions)
- **Email**: support@nucap.pk

---

<div align="center">

**Made with ❤️ for Pakistani Students**

⭐ Star us on GitHub if you find this project helpful!

[⬆ Back to Top](#-nucap---national-university-admission-platform)

</div>
