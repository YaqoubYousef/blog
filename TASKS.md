# ✅ Laravel Blog Website CRUD Project – Task List

## Phase 1: Project Setup
- [x] Create new Laravel project  
- [x] Configure database connection  
- [x] Install & set up authentication system (Laravel Breeze recommended)  

---

## Phase 2: Database Design
- [x] Modify `users` table migration (add `usertype` enum: admin/normal)  
- [x] Create `categories` table migration (with soft deletes)  
- [x] Create `posts` table migration (with `user_id`, `category_id`, `status`)  
- [x] Run all migrations  

---

## Phase 3: Models & Relationships
- [x] Update `User` model  
  - [x] Add `posts()` relationship  
  - [x] Add `isAdmin()` helper method  
- [x] Create `Category` model  
  - [x] Enable soft deletes  
  - [x] Add `posts()` relationship  
- [x] Create `Post` model  
  - [x] Add `user()` and `category()` relationships  
  - [x] Define `$fillable` fields  

---

## Phase 4: Authorization & Middleware
- [x] Create `AdminMiddleware` for admin-only routes  
- [x] Define role-based access control  
- [x] Implement ownership checks for posts (user can edit/delete only their own posts)  

---

## Phase 5: Controllers
- [x] `PostController` – CRUD operations (with ownership validation)  
- [x] `CategoryController` – Admin-only CRUD (with soft delete + restore)  
- [x] `AdminController` – Dashboard & management features  

---

## Phase 6: Routes Structure
### Public Routes
- [x] GET `/` – homepage (list published posts)  
- [x] GET `/posts/{slug}` – view single post  
- [x] Auth routes (login, register, etc.)  

### Authenticated User Routes
- [x] GET `/dashboard` – user dashboard  
- [x] GET `/my-posts` – user’s posts  
- [x] POST `/posts` – create post  
- [x] GET `/posts/{id}/edit` – edit own post  
- [x] PUT `/posts/{id}` – update own post  
- [x] DELETE `/posts/{id}` – delete own post  

### Admin Routes
- [ ] GET `/admin/dashboard`  
- [ ] GET `/admin/posts` – manage all posts  
- [ ] CRUD `/admin/categories` – manage categories  
- [ ] PUT/DELETE `/admin/posts/{id}` – edit/delete any post  

---

## Phase 7: Views & Frontend
- [x] **Public Views**: homepage, single post, category-filtered posts  
- [ ] **User Dashboard Views**: my posts, create/edit forms, profile management  
- [ ] **Admin Views**: dashboard, posts management, category management (with restore)  

---

## Phase 8: Features Implementation
- [x] **Post features**:  
  - [x] Rich text editor for post content  
  - [x] Slug auto-generation from title  
  - [x] Draft/Published status toggle  
  - [x] Category selection dropdown  
  - [x] Excerpt auto-generation or manual input  
- [x] **Category features**:  
  - [x] Category creation with validation  
  - [x] Soft delete implementation  
  - [x] Restore deleted categories (admin only)  
  - [x] Post count per category  
  - [x] Category slug generation  
- [x] **User Experience features**:  
  - [x] Pagination for post listings  
  - [x] Search functionality  
  - [x] Category filtering  
  - [x] Responsive design  
  - [x] Flash messages for user feedback  

---

## Phase 9: Validation Rules
- [x] **Post validation**:  
  - Title: required, max 255 characters, unique  
  - Content: required  
  - Category: required, must exist  
  - Status: required, in `['draft','published']`  
- [x] **Category validation**:  
  - Name: required, max 255 characters, unique  
  - Slug: required, unique, URL-friendly  
  - Description: optional, max 1000 characters  
- [x] **User validation**:  
  - Name: required, max 255 characters  
  - Email: required, email format, unique  
  - Password: required, min 8 characters, confirmed  
  - Usertype: required, in `['admin','normal']`  

---

## Phase 10: Security
- [ ] Implement authorization policies  
- [ ] Hash passwords  
- [ ] Sanitize input & protect against XSS  
- [x] Enable CSRF protection  
- [ ] Validate slugs properly  

---

## Phase 11: Testing Scenarios
- [x] **User Role Testing**:  
  - Normal user cannot access admin routes  
  - Normal user cannot edit others’ posts  
  - Admin can manage all content  
  - Proper redirects for unauthorized access  
- [x] **CRUD Operations Testing**:  
  - Create posts with required fields  
  - Update posts maintaining relationships  
  - Soft delete categories & verify posts remain  
  - Restore deleted categories  
- [ ] **Data Integrity Testing**:  
  - Foreign key constraints work properly  
  - Cascade deletes function correctly  
  - Unique constraints prevent duplicates  
  - Validation prevents invalid data  
