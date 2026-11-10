# Conveyor Uni Express (CUX)

Web application and management system for Conveyor Uni Express international courier and logistics operations, featuring public shipment tracking, rate quotation, and an administrative control panel.

---

## 🚀 Getting Started (For Developers)

Follow these steps to set up the project on your local machine:

### 1. Prerequisites
- **PHP**: 8.2 or higher
- **Composer**: 2.x
- **Node.js**: 18.x or higher & **npm**
- **MySQL / MariaDB** (or XAMPP)

---

### 2. Installation Steps

1. **Clone the repository** (if you haven't already):
   ```bash
   git clone <repository-url>
   cd <project-folder>
   ```

2. **Install PHP dependencies**:
   ```bash
   composer install
   ```

3. **Install Frontend dependencies**:
   ```bash
   npm install
   ```

4. **Environment Setup**:
   Copy the example environment file:
   ```bash
   cp .env.example .env
   ```
   Generate the application encryption key:
   ```bash
   php artisan key:generate
   ```

5. **Configure Database**:
   - Create a database in MySQL (e.g., named `conveyor_uniexpress`).
   - Check `.env` and configure your database credentials:
     ```env
     DB_CONNECTION=mysql
     DB_HOST=127.0.0.1
     DB_PORT=3306
     DB_DATABASE=conveyor_uniexpress
     DB_USERNAME=root
     DB_PASSWORD=
     ```

6. **Run Migrations & Seeders**:
   ```bash
   php artisan migrate --seed
   ```

7. **Create Storage Symbolic Link**:
   ```bash
   php artisan storage:link
   ```

8. **Build Assets & Start Development Server**:
   In one terminal tab:
   ```bash
   npm run dev
   ```
   In another terminal tab:
   ```bash
   php artisan serve
   ```
   Access the application at [http://127.0.0.1:8000](http://127.0.0.1:8000).

---

## 🔐 Default Seed Credentials

After running `php artisan migrate --seed`, the following accounts are available for testing:

| Role | Email | Password |
|---|---|---|
| **Super Admin** | `admin@conveyoruniexpress.com` | `password123` |
| **Operations Desk** | `opx.cux@conveyor.com.bd` | `password123` |

### Sample Tracking Numbers for Testing:
- `CUX-892415-BD`
- `CUX-741982-UK`
- `CUX-630291-SG`
- `CUX-519284-HK`

---

## 📁 Key Directories & Architecture
- **`app/Http/Controllers/Frontend/`**: Public portal controllers (Tracking, Rate Calculator, Pages).
- **`app/Http/Controllers/Admin/`**: Management dashboard, shipments, contacts, and news.
- **`app/Models/`**: Eloquent models (`Shipment`, `Checkpoint`, `QuoteRequest`, etc.).
- **`resources/views/`**: Blade template layouts and pages (Frontend & Admin).
- **`routes/web.php`**: All application web routes.

---

## 🛡️ Git Workflow Best Practices
- **Do not commit `.env`**: `.env` contains local environment secrets and should never be pushed to version control.
- **Branching**: Create feature branches (`git checkout -b feature/your-feature-name`) and create Pull Requests for review.
