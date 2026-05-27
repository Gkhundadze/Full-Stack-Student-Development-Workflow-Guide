# Full-Stack-Student-Development-Workflow-Guide# Full-Stack Student Development Workflow Guide
## Git Branching Strategy, Team Rules, Trello Workflow & Collaboration Standards

---

# მიზანი

ეს დოკუმენტი განსაზღვრავს სტუდენტური Full-Stack პროექტების განვითარების პროცესს.

დოკუმენტის მიზანია:

- ქაოსის შემცირება
- გუნდური მუშაობის სტანდარტიზაცია
- Git-ის სწორი გამოყენების სწავლება
- პასუხისმგებლობების გამიჯვნა
- რეალური სამუშაო პროცესის სიმულაცია
- Pull Request და Code Review კულტურის დანერგვა
- Frontend / Backend არქიტექტურის სწორად გააზრება

---

# პროექტის ძირითადი არქიტექტურა

პროექტი იყოფა ორ ძირითად ნაწილად:

## Frontend

რაც მუშაობს ბრაუზერში:

- UI
- React Components
- Forms
- State Management
- Routing
- Client-side Validation
- API Requests
- Styling

---

## Backend

რაც მუშაობს სერვერზე:

- Express Routes
- Controllers
- Database Operations
- Authentication
- Middleware
- Business Logic
- API Responses

---

# Git Branching Strategy

## ძირითადი Branch-ები

```bash
main
develop
frontend/*
backend/*
feature/*
bugfix/*
refactor/*
```

---

# Branch-ების დანიშნულება

## 1. main

### დანიშნულება

სტაბილური და მუშა ვერსია.

### წესები

- პირდაპირი push აკრძალულია
- მხოლოდ Pull Request-ით განახლდება
- ყოველთვის უნდა მუშაობდეს
- გამოიყენება საბოლოო დემოსთვის

---

## 2. develop

### დანიშნულება

ძირითადი სამუშაო branch.

ყველა feature ჯერ develop-ში ერთიანდება.

### წესები

- ყველა feature იწყება develop-დან
- main-ში merge მხოლოდ develop-დან ხდება
- develop შეიძლება იყოს ნაწილობრივ დაუმთავრებელი

---

# Frontend Branch-ები

## ფორმატი

```bash
frontend/task-name
```

---

## მაგალითები

```bash
frontend/login-page
frontend/navbar-ui
frontend/product-cards
frontend/cart-page
frontend/form-validation
frontend/profile-settings
```

---

## Frontend Branch-ში დასაშვები ცვლილებები

### შეიძლება:

- React Components
- CSS
- Tailwind
- UI Logic
- Form Validation
- State Updates
- Fetch / Axios Calls
- Routing

### არ შეიძლება:

- Database Logic
- Express Routes
- Server Authentication
- Backend Business Logic

---

# Backend Branch-ები

## ფორმატი

```bash
backend/task-name
```

---

## მაგალითები

```bash
backend/auth-login
backend/products-api
backend/user-model
backend/cart-service
backend/payment-endpoint
backend/orders-controller
```

---

## Backend Branch-ში დასაშვები ცვლილებები

### შეიძლება:

- Express Routes
- Controllers
- MongoDB Logic
- Mongoose Models
- Middleware
- Authentication
- Authorization
- API Logic

### არ შეიძლება:

- Frontend UI
- CSS
- React Components
- Layout ცვლილებები

---

# Feature Branch-ები

## დანიშნულება

Frontend + Backend ინტეგრაცია.

ეს branch გამოიყენება მაშინ, როცა ორივე მხარე მზადაა და საჭიროა საბოლოო ინტეგრაცია.

---

## ფორმატი

```bash
feature/task-name
```

---

## მაგალითები

```bash
feature/auth-system
feature/cart-flow
feature/checkout-system
feature/profile-management
```

---

# Bugfix Branch-ები

## დანიშნულება

არსებული პრობლემების გამოსწორება.

---

## ფორმატი

```bash
bugfix/task-name
```

---

## მაგალითები

```bash
bugfix/login-error
bugfix/mobile-layout
bugfix/cart-total
bugfix/token-validation
```

---

# Refactor Branch-ები

## დანიშნულება

კოდის გაუმჯობესება ფუნქციონალის შეცვლის გარეშე.

---

## ფორმატი

```bash
refactor/task-name
```

---

## მაგალითები

```bash
refactor/navbar-component
refactor/auth-service
refactor/folder-structure
```

---

# Branch Naming Rules

## აუცილებელი წესები

### გამოიყენეთ:

- lowercase
- dash-separated names
- descriptive naming

---

## სწორი მაგალითები

```bash
frontend/login-page
backend/create-product-api
feature/auth-system
```

---

## არასწორი მაგალითები

```bash
frontend/test
frontend/new
backend/final-version
feature/stuff
```

---

# Task Splitting Strategy

## მთავარი წესი

ერთი branch = ერთი პასუხისმგებლობა.

---

## ცუდი მაგალითი

```bash
feature/login-ui-api-db-all-in-one
```

რატომ არის ცუდი:

- რთულია review
- რთულია debugging
- merge conflicts იზრდება
- პასუხისმგებლობები ირევა

---

## სწორი მაგალითი

```bash
backend/auth-login
frontend/login-form
feature/auth-system
```

---

# Recommended Development Order

## Full-Stack Feature Workflow

### 1. Backend Development

პირველად მზადდება API.

მაგალითი:

```bash
backend/auth-login
```

იქმნება:

- Route
- Controller
- Database Logic
- Token Logic
- API Response

---

### 2. Frontend Development

შემდეგ იქმნება UI.

მაგალითი:

```bash
frontend/login-page
```

იქმნება:

- Form
- Validation
- UI States
- Axios Request
- Error Handling

---

### 3. Integration

ორივე ნაწილის გაერთიანება.

```bash
feature/auth-system
```

---

# Git Workflow

# 1. პროექტის განახლება

ყოველთვის მუშაობის დაწყებამდე:

```bash
git checkout develop
git pull origin develop
```

---

# 2. ახალი Branch-ის შექმნა

```bash
git checkout -b frontend/login-page
```

ან:

```bash
git checkout -b backend/auth-login
```

---

# 3. Commit-ები

## Commit წესები

- იყოს პატარა
- აღწერდეს კონკრეტულ ცვლილებას
- იყოს გასაგები

---

## კარგი commit მაგალითები

```bash
git commit -m "Create login form UI"
git commit -m "Add form validation"
git commit -m "Implement JWT authentication"
```

---

## ცუდი commit მაგალითები

```bash
git commit -m "fix"
git commit -m "update"
git commit -m "changes"
```

---

# 4. Push

```bash
git push origin frontend/login-page
```

---

# 5. Pull Request

PR იქმნება:

```bash
frontend/login-page → develop
```

ან:

```bash
backend/auth-login → develop
```

---

# Pull Request Rules

## აუცილებელია

- მოკლე აღწერა
- რა შეიცვალა
- როგორ ტესტდება
- screenshot თუ UI შეიცვალა

---

# Code Review Rules

## Review-ის დროს შემოწმდეს

- კოდის სისუფთავე
- naming consistency
- unnecessary code
- responsiveness
- console errors
- API error handling
- security basics
- reusable components

---

# Merge Rules

## აკრძალულია

- პირდაპირ merge main-ში
- merge review-ის გარეშე
- broken code merge

---

## დაშვებულია

- merge develop-ში review-ის შემდეგ
- main-ში merge მხოლოდ სტაბილური ვერსიისთვის

---

# Trello Workflow

# Recommended Columns

```text
Backlog
To Do
In Progress
Code Review
Testing
Done
```

---

# Trello Card Structure

## თითოეული Card უნდა შეიცავდეს:

### 1. Task Title

მაგალითი:

```text
Create Login Page
```

---

### 2. Branch Name

```text
frontend/login-page
```

---

### 3. Task Type

```text
Frontend
```

ან:

```text
Backend
```

---

### 4. Definition of Done

Checklist:

- branch created
- functionality completed
- tested locally
- pushed to GitHub
- pull request created
- review passed

---

# Team Responsibility Rules

## Frontend Developer

პასუხისმგებელია:

- UI
- UX
- Components
- Styling
- Client Logic
- API Consumption

---

## Backend Developer

პასუხისმგებელია:

- API
- Database
- Authentication
- Server Logic
- Validation
- Security

---

## Full-Stack Integrator

პასუხისმგებელია:

- Frontend + Backend Integration
- Final Testing
- Conflict Resolution
- Release Preparation

---

# Conflict Prevention Rules

## არასოდეს:

- იმუშაოთ ერთსა და იმავე branch-ზე
- შეცვალოთ ერთმანეთის ფაილები შეთანხმების გარეშე
- merge გააკეთოთ pull-ის გარეშე

---

# Merge Conflict Prevention

## ხშირად გააკეთეთ:

```bash
git pull origin develop
```

---

## პატარა branch-ები გამოიყენეთ

დიდი branch-ები ქმნის:

- merge conflicts
- review პრობლემებს
- debugging სირთულეს

---

# Recommended Task Size

## ერთი task:

- მაქსიმუმ 1-2 საათი
- კონკრეტული პასუხისმგებლობა
- ერთი მიზანი

---

## თუ task დიდია:

გაყავით ნაწილებად.

მაგალითი:

```text
frontend/login-ui
frontend/login-validation
backend/login-api
feature/auth-system
```

---

# Security Rules

## აკრძალულია

- passwords GitHub-ზე ატვირთვა
- .env commit
- secret keys commit
- Mongo URI commit

---

# აუცილებელია .gitignore

```bash
node_modules
.env
/dist
```

---

# Recommended Repository Structure

## Frontend

```text
frontend/
 ├── src/
 ├── components/
 ├── pages/
 ├── services/
 ├── hooks/
 ├── context/
 └── styles/
```

---

## Backend

```text
backend/
 ├── routes/
 ├── controllers/
 ├── models/
 ├── middleware/
 ├── services/
 ├── config/
 └── utils/
```

---

# Git Discipline Rules

## არასოდეს:

- commit broken code
- push console.log spam
- ignore review comments
- create giant PRs
- push directly to main

---

## ყოველთვის:

- pull before work
- create separate branch
- use meaningful commits
- review your code
- test before push

---

# Final Recommended Workflow

## სრული პროცესი

```text
1. Trello Task Created
2. Student Pulls Latest Develop
3. Student Creates Branch
4. Development Starts
5. Small Commits
6. Push to GitHub
7. Pull Request Created
8. Code Review
9. Merge to Develop
10. Testing
11. Stable Version → Main
```

---

# საბოლოო პრინციპი

## მთავარი იდეა

Frontend და Backend არის დამოუკიდებელი პასუხისმგებლობები.

Git Workflow-ის მიზანია:

- პასუხისმგებლობების გამიჯვნა
- კონტროლის გამარტივება
- Review პროცესის გაუმჯობესება
- გუნდური მუშაობის სწავლება
- რეალური განვითარების პროცესის სიმულაცია

---

# რეკომენდაცია სტუდენტებისთვის

"პატარა branch-ები, პატარა commit-ები, მკაფიო პასუხისმგებლობები და ხშირი review — ეს არის სტაბილური გუნდის საფუძველი."

