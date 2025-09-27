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
- [ ] Create `AdminMiddleware` for admin-only routes  
- [ ] Define role-based access control  
- [ ] Implement ownership checks for posts (user can edit/delete only their own posts)  

---

## Phase 5: Controllers
- [x] `PostController` – CRUD operations (with ownership validation)  
- [ ] `CategoryController` – Admin-only CRUD (with soft delete + restore)  
- [ ] `AdminController` – Dashboard & management features  

---

## Phase 6: Routes Structure
### Public Routes
- [ ] GET `/` – homepage (list published posts)  
- [ ] GET `/posts/{slug}` – view single post  
- [ ] Auth routes (login, register, etc.)  

### Authenticated User Routes
- [ ] GET `/dashboard` – user dashboard  
- [ ] GET `/my-posts` – user’s posts  
- [ ] POST `/posts` – create post  
- [ ] GET `/posts/{id}/edit` – edit own post  
- [ ] PUT `/posts/{id}` – update own post  
- [ ] DELETE `/posts/{id}` – delete own post  

### Admin Routes
- [ ] GET `/admin/dashboard`  
- [ ] GET `/admin/posts` – manage all posts  
- [ ] CRUD `/admin/categories` – manage categories  
- [ ] PUT/DELETE `/admin/posts/{id}` – edit/delete any post  

---

## Phase 7: Views & Frontend
- [ ] **Public Views**: homepage, single post, category-filtered posts  
- [ ] **User Dashboard Views**: my posts, create/edit forms, profile management  
- [ ] **Admin Views**: dashboard, posts management, category management (with restore)  

---

## Phase 8: Features Implementation
- [ ] **Post features**:  
  - [ ] Rich text editor for post content  
  - [ ] Slug auto-generation from title  
  - [ ] Draft/Published status toggle  
  - [ ] Category selection dropdown  
  - [ ] Excerpt auto-generation or manual input  
- [ ] **Category features**:  
  - [ ] Category creation with validation  
  - [ ] Soft delete implementation  
  - [ ] Restore deleted categories (admin only)  
  - [ ] Post count per category  
  - [ ] Category slug generation  
- [ ] **User Experience features**:  
  - [ ] Pagination for post listings  
  - [ ] Search functionality  
  - [ ] Category filtering  
  - [ ] Responsive design  
  - [ ] Flash messages for user feedback  

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
- [ ] **User Role Testing**:  
  - Normal user cannot access admin routes  
  - Normal user cannot edit others’ posts  
  - Admin can manage all content  
  - Proper redirects for unauthorized access  
- [ ] **CRUD Operations Testing**:  
  - Create posts with required fields  
  - Update posts maintaining relationships  
  - Soft delete categories & verify posts remain  
  - Restore deleted categories  
- [ ] **Data Integrity Testing**:  
  - Foreign key constraints work properly  
  - Cascade deletes function correctly  
  - Unique constraints prevent duplicates  
  - Validation prevents invalid data  
