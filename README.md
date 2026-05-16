# EcoRoute

**EcoRoute** is a smart, community-driven navigation application designed to help urban commuters reduce their carbon footprint while optimizing travel time and cost. By integrating real-time traffic data, public transit schedules, and weather conditions, EcoRoute provides multi-modal travel options that prioritize low-emission paths.

---

## 🚀 Architecture Overview
EcoRoute is built as a **monorepo** to ensure clean dependency management and synchronized development between the frontend and backend.

*   **Frontend:** A responsive React application that provides the user interface for route searching, dashboard visualization, and social interaction.
*   **Backend:** A robust Express.js API that handles routing algorithms, carbon emission calculations, and user authentication.
*   **Database:** PostgreSQL, managed via Prisma ORM, providing a structured schema for users, routes, points, and community challenges.
*   **Communication:** RESTful API for standard operations, with Socket.io integration for real-time point updates.

---

## 🛠 Technology Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend** | React, Zustand, Axios, React-Leaflet |
| **Backend** | Express.js, Prisma ORM, JWT, Socket.io |
| **Database** | PostgreSQL |
| **Deployment** | Vercel (Frontend/Serverless Functions) |
| **Testing** | Jest, Supertest, Cypress, React Testing Library |

---

## 📊 Project Summary
*   **Total Phases:** 7
*   **Total Issues:** 40+
*   **Focus:** Infrastructure setup, algorithmic routing, gamification, and robust testing/deployment pipelines.

---

## 🏗 Development Phases

1.  **Foundation & Infrastructure:** Monorepo setup, database schema definition, and CI/CD pipeline configuration.
2.  **Core Backend Services:** Implementation of JWT auth, Dijkstra-based routing engine, and carbon calculation logic.
3.  **Frontend UI Development:** Building the responsive shell, dashboard, and search interfaces.
4.  **Integration Layer:** Connecting the frontend to the backend via Axios interceptors and real-time WebSocket syncing.
5.  **Quality Assurance:** Implementing unit, integration, and E2E testing frameworks.
6.  **Production Deployment:** Configuring production environments, SSL, and monitoring (Sentry/Analytics).
7.  **Documentation:** Finalizing API specs (OpenAPI/Swagger), architecture guides, and contribution standards.

---

## 🏁 Getting Started

### Prerequisites
*   Node.js (v18+)
*   PostgreSQL
*   NPM or Yarn

### Installation
1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd ecoroute
   ```
2. **Install dependencies:**
   ```bash
   npm install
   ```
3. **Configure Environment Variables:**
   Copy the `.env.example` files in both `/client` and `/server` to `.env` and populate them with your local database and API credentials.
4. **Initialize Database:**
   ```bash
   npx prisma migrate dev
   ```
5. **Start Development:**
   ```bash
   npm run dev
   ```

---

## 📝 Implementation Notes

*   **Routing:** The routing engine uses a custom Dijkstra implementation; focus on performance by utilizing Redis for caching frequent routes.
*   **Gamification:** Carbon savings are calculated using the formula: `(Car_CO2 - Selected_CO2) * distance`. Ensure floating-point precision is handled using a decimal math library.
*   **Security:** All API requests must include a JWT in the `Authorization` header. Sensitive keys must never be committed to version control; use GitHub Secrets for CI/CD and Vercel environment variables for production.
*   **Performance:** Use `React.memo` and `useCallback` for map-heavy components to prevent unnecessary re-renders during location updates.

---

## 🤝 Contribution
Please refer to the `CONTRIBUTING.md` file for guidelines on branch naming conventions, commit standards, and the pull request review process.