# Azadi Menu Management System – Project Plan

## Overview
A modern, animated, multilingual menu and management system for "Azadi" café/bookstore, built with Next.js, MySQL, and TailwindCSS. Supports Kurdish (RTL), Arabic (RTL), and English (LTR). Features a beautiful user menu and a powerful admin dashboard for easy management.

---

## 1. Features

### User-Facing Menu
- Multilingual: Kurdish (RTL), Arabic (RTL), English (LTR)
- Animated, modern UI (TailwindCSS, Framer Motion)
- Browse by category (books, stationery, Hajj/Umrah, hot/cold drinks)
- View item details: image, description, size, price
- Filter/search by category or name
- Language switcher (RTL/LTR auto-switch)
- Responsive (mobile/tablet/desktop)

### Admin Dashboard
- Secure login/authentication
- Add/edit/delete categories
- Add/edit/delete items (with images, description, size, price, translations)
- Manage item sizes (e.g., drink sizes)
- Upload/manage images
- Manage translations for all fields
- Dashboard analytics (optional: sales, popular items)

---

## 2. Menu Structure (All Languages)

### Books
- بەشێ پەرتووكان | قسم الكتب | Books Section
- بەشێن كوردی | قسم الكردي | Kurdish Books
- رۆمان | روايات | Novels
- گەشپێدان | تطوير الذات | Self-Development
- ئاینی | ديني | Religious
- بەشێ عەرەبی | قسم العربي | Arabic Books
- بەشێ انگلیزی | قسم الانجليزي | English Books

### Stationery
- بەشێ پەرگەهێ | قسم القرطاسية | Stationery Section
- پێنوس | اقلام | Pens
- ستیكەر | ملصقات | Stickers
- دەفتەر | دفاتر | Notebooks

### Hajj & Umrah Supplies
- پێدڤیاتێ حەج و عومرێ | مستلزمات الحج والعمرة | Hajj & Umrah Supplies
- دەرسوك | دروسوك | Drawstring Bag
- سیواك | سواك | Siwak
- تزبیح | مسبحة | Tasbeeh

### Hot Drinks
- ڤەخوارنێن گەرم | مشروبات ساخنة | Hot Drinks
- قهوە تركی | قهوة تركية | Turkish Coffee
- قهوە عربی | قهوة عربية | Arabic Coffee
- چوكلێت | شوكولاتة ساخنة | Hot Chocolate
- قهوە كەزان | قهوة كزان | Kazan Coffee

### Cold Drinks
- ڤەخوارنێن تەزی | مشروبات باردة | Cold Drinks
- ئایس كافی | ايس كوفي | Iced Coffee

---

## 3. Database Schema (MySQL)
- **users**: id, username, password_hash, role (admin/user)
- **categories**: id, parent_id, image_url, order
- **category_translations**: id, category_id, language, name, description
- **items**: id, category_id, image_url, base_price, order
- **item_translations**: id, item_id, language, name, description
- **item_sizes**: id, item_id, size_label, price_delta
- **item_images**: id, item_id, image_url

---

## 4. Next.js App Structure
- `/pages`
  - `/api` (CRUD endpoints for categories, items, images, sizes, auth)
  - `/admin` (dashboard, login, management pages)
  - `/menu` (user-facing menu)
  - `/` (landing page)
- `/components`
  - `MenuGrid`, `CategoryCard`, `ItemCard`, `LanguageSwitcher`, `AdminSidebar`, `AdminForm`, etc.
- `/lib` (db, auth, utils)
- `/public/uploads` (images)

---

## 5. UI/UX Design
- TailwindCSS for all styling
- Framer Motion for animations (hover, transitions, modals)
- RTL/LTR support via `dir` attribute and Tailwind plugins
- Colorful, inviting palette (café/bookstore vibe)
- Animated category/item cards
- Admin dashboard: clean, tabbed, sortable tables, modals for add/edit
- Image upload with preview

---

## 6. Admin Features
- Login/logout
- Add/edit/delete categories (with images, translations)
- Add/edit/delete items (with images, sizes, translations)
- Manage item sizes (e.g., small/medium/large for drinks)
- Upload/manage images
- Manage translations for all fields
- Dashboard analytics (optional)

---

## 7. User Features
- Browse menu by category
- Filter/search items
- View item details (image, description, size, price)
- Switch language (Kurdish, Arabic, English)
- Responsive and animated UI

---

## 8. Deployment & Windows Setup
- Use WSL2 or Docker for MySQL on Windows
- `npm install` for dependencies
- `.env` for DB credentials
- `next dev` for local development
- `next build && next start` for production
- Image uploads: `/public/uploads` or S3 (optional)

---

## 9. Stretch Goals
- User accounts (favorites, orders)
- POS integration
- Analytics dashboard
- Mobile app (React Native)

---

## 10. References
- [Next.js Documentation](https://nextjs.org/docs)
- [TailwindCSS](https://tailwindcss.com/)
- [Framer Motion](https://www.framer.com/motion/)
- [MySQL](https://dev.mysql.com/doc/)
- [RTL/LTR Tailwind Guide](https://tailwindcss.com/docs/rtl-support)

---

**Project Name:** Azadi Menu Management System
**Location:** Azadi Café/Bookstore
**Languages:** Kurdish, Arabic, English