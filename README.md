# 📦 Simple Stock Management System (SSMS)

A lightweight, role-based inventory and stock tracking system designed for small to mid-sized teams. Built with simplicity, clarity, and hierarchy in mind. 

## 🔐 Role-Based Access Control

| Feature                              | Admin        | Manager               | Staff              |
|--------------------------------------|--------------|------------------------|--------------------|
| Add Users                            | ✅ Manager, Staff | ✅ Staff only        | ❌                 |
| Create Category / Sub-Category       | ✅           | ❌                     | ❌                 |
| Add Items                            | ❌           | ✅                     | ❌                 |
| View Cost Price                      | ✅           | ✅                     | ❌                 |
| View Target & Sell Price             | ✅           | ✅                     | ✅                 |
| Stock In                             | ✅           | ✅                     | ❌                 |
| Stock Out                            | ✅           | ✅                     | ✅                 |
| Commission Calculator (5% / RM10)    | ✅ Editable   | ✅ Editable           | ✅ Use Only        |
| View Reports / Audit Log             | ✅           | ✅                     | ❌                 |

---

## 🧱 System Modules

### Admin Dashboard
- Add Managers & Staff
- Create Categories / Subcategories
- Access Audit Logs & Full Reports

### Manager Dashboard
- Add Staff
- Add / Edit Items
- Manage Stock (In/Out)
- View and Edit Pricing
- Set Commission Rules

### Staff Dashboard
- Stock Out Only
- View Target & Sell Prices
- Access Commission Calculator (preset only)

---

## 🗃️ Database Schema (Simplified)

- **Users**: `id`, `name`, `email`, `role`, `created_by`
- **Categories / SubCategories**
- **Items**: `cost_price`, `target_price`, `sell_price`, `quantity`
- **StockLogs**: `item_id`, `type`, `quantity`, `user_id`
- **CommissionSettings**: `type (percent/fixed)`, `value`

---

## 💡 Key Features

- 🔁 Commission Calculator (5% or RM10)
- ⚠️ Low Stock Alerts
- 🧾 Audit Logging
- 📱 Mobile-Friendly UI
- ♻️ Soft Delete / Restore

---

## 🚀 Tech Stack

- **Backend**: Laravel 10
- **Frontend**: Blade + Bootstrap 5
- **Database**: MySQL 8
- **Admin Panel**: Laravel Breeze / AdminLTE
- **Auth**: Laravel Sanctum (for API/mobility)
- **Optional**: Vue.js for reactive frontend

---

## 📷 UI Preview

![Stock System UI Mockup](mockup.png)

---

## 📂 Project Setup

```bash
# Clone repo
git clone https://github.com/your-org/ssms.git
cd ssms

# Install dependencies
composer install
npm install && npm run dev

# Setup environment
cp .env.example .env
php artisan key:generate

# Migrate & seed
php artisan migrate --seed

# Run server
php artisan serve
