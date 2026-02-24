# 🤝 Contributions

Thank you for contributing to this project.

## General Guidelines
- All code and documents must be written in **English**.
- All functions must have a description of what they do before their declaration. **In the Backend, parameters and business logic must be especially detailed.**
- All files must have a description at the top, including the last edit date and authors in the comment. **If a fix is made, the author of that correction must be specified in the header.**
- Files must not exceed 1000 lines; if exceeded, split them.
- For functions within files, input arguments, title, and purpose must be included.
- At the top of each file, the modification date and file contents must be included.

---

## 👥 Team Segmentation

To optimize development among the 10 members, the team is divided into:

### Project Manager
**Responsibility:** Plan the work schedule, track progress, and coordinate team communication.
- `Sergio Xuan`

### Leader Architecture
**Responsibility:** Technical design and architectural decisions for the entire system.
- `Julio César Rodríguez`

### Frontend Team
**Responsibility:** UI and state management in React.
- `Rebeca Davila Araiza` — Team Lead.
- `Nicolas Quintana`
- `Fausto Izquierdo`

### Backend & Database Team
**Responsibility:** API, services, and database in NestJS.
- `Santiago Coronado` — Team Lead.
- `Diego de la Vega`
- `Jin Sik Yoon`
- `Sebastian Borjas`
- `Juan Pablo Narchi`

### QA
**Responsibility:** Responsible for reviewing Pull Requests and verifying the functionality of what is currently being implemented. Members will rotate over time so everyone can review quality.

### Testing
**Responsibility:** The entire team will carry out the tests outlined in the test plan.

---

## Naming Conventions

### For Code

- **camelCase**
    - Variables
      ```
        myVar, i
      ```
    - Objects/JSON
      ```
        myObject, myJSON, appService
      ```
    - Functions, methods
      ```
        myFunction(), getOne(), Class.methodOne()
      ```
- **PascalCase**
    - Classes
      ```
        MyClass, AppService
      ```
    - Types
        ```
        MyType, Point
        ```
    - Interfaces
        ```
        MyInterface, Person
        ```
    - Decorators
        ```
        @Decorator(), @Get()
        ```
- **ALLCAPS**
    - Constant variables
        ```
        COLORS, WIDTH
        ```
    - Environment variables
        ```
        process.env.CONSTANT, process.env.POSTGRES_USER
        ```

### For Folders and Files

File and folder names must clearly convey the content of the file, following this format:

#### Folder names starting with lowercase:
```
Correct:
components/
pages/
assets/
hooks/
utils/
config/
types/

Incorrect:
Components/
Pages/
Assets/
Hooks/
```

#### File names for components or pages:
```
Correct:
Login.tsx
Register.tsx
Dashboard.tsx
Bookings.tsx
CreateTravelRequest.tsx
EditTravelRequest.tsx
RequestInfo.tsx
Requests.tsx
Error.tsx

Incorrect:
login.tsx
register.tsx
dashboard.tsx
create_travel_request.tsx
```

## Example Project File Structure
```
frontend/
├── src/
│   ├── components/   # Reusable components
│   ├── pages/        # Main views/pages (Login.tsx, Dashboard.tsx, etc.)
│   ├── hooks/        # Custom hooks (useAuth, etc.)
│   ├── utils/        # Helper functions
│   ├── assets/       # Images, icons, fonts
│   ├── config/       # Configuration files
│   └── types/        # TypeScript type definitions
└── public/
```

### For the Database

Database table names in plural, column names in singular.

- **snake_case**
    - Columns
      ```
        id, name, email
      ```
    - Tables
      ```
        approved_trips, user_roles, assistants, preferences
      ```
    - Databases
      ```
        users, trips, db
      ```
    - Schemas
      ```
        public
      ```
---

## 🧠 GitFlow

We follow the [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/) model:

| Branch        | Purpose                                          |
|---------------|--------------------------------------------------|
| `main`        | Production-ready code (final deliverables).      |
| `develop`     | Latest stable development version.               |
| `feature/*`   | New features.                                    |
| `bugfix/*`    | Bug fixes.                                       |
| `release/*`   | Preparation for a new version (Weeks 3 and 5).   |

### Note on the Stability Flow (Release Branches)

The transition from `develop` to `main` is not direct. `release/*` branches are required:

1. **Isolation for the Deliverable:** When a milestone is reached, a `release/name-or-area/vX.Y.Z` branch is created. This creates a code freeze for that version, allowing the development team to continue working on new features in `develop` without affecting the stability of what is being delivered.

2. **Rigorous Validation:** This branch is the exclusive environment for running the test plan. Both functional requirements (Global Operations Map flows) and non-functional requirements (security, load, and portability) are validated here. Only if the system passes these validations without critical errors is it considered stable.

3. **Quality Assurance in `main`:** The `main` branch exclusively represents finished, tested, and approved versions signed off by the Backend, Frontend, and QA teams. Using a `release/*` branch as a filter prevents accidental integration errors.

4. **Closing the Cycle:** Once the deliverable is submitted, the `release/*` branch is merged into `main` (tagged with its corresponding version) and also reintegrated into `develop` to ensure any last-minute fixes are carried forward into future development.

---

## 💬 Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/):

**type**(area): message

| Type       | When to use it                                          |
|------------|---------------------------------------------------------|
| `feat`     | New features                                            |
| `fix`      | Bug fixes                                               |
| `docs`     | Documentation changes                                   |
| `style`    | Formatting changes (spaces, commas)                     |
| `refactor` | Code restructuring without changing functionality       |
| `test`     | Adding or modifying tests                               |
| `chore`    | Maintenance tasks (builds, dependencies)                |

### 💡 Examples:
- `feat(frontend): add login screen`
- `fix(auth): fix token bug`

---

## ✅ Pull Request Process

All PRs must meet the following checklist before being merged:

- [ ] The branch starts from `develop`
- [ ] The feature is tested and working
- [ ] The code follows formatting and style standards
- [ ] The commit follows the convention (`feat:`, `fix:`, etc.)
- [ ] Documentation has been updated (if applicable)

⚠️ No one may approve their own PR, regardless of the target branch.

### Approval by target branch

- **To `develop`:** Requires approval from at least 1 or 2 members of the **same team** that opened the PR.
- **To `main` (via `release/*`):** Requires approval from **QA** and the **Team Lead** of the corresponding team (e.g. Frontend Lead if it's a frontend PR).
