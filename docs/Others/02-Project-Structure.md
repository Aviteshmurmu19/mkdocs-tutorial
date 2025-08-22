# A Guide to Project Structure

Our project structure is designed for three core principles: **scalability**, **consistency**, and **automation**. The goal is to allow the project to grow infinitely without needing to manually update a central configuration file.

This is achieved through a logical folder hierarchy combined with small, localized navigation files.

#### The Golden Rule: One Folder, One Course

The entire system is built around a single, simple idea: **every course gets its own folder.**

This makes the structure predictable and self-contained. All notes, images, and resources for a specific course live inside that course's dedicated folder, making it easy to manage, update, or move.

---

#### The Anatomy of the `docs` Directory

Every file and folder for your site lives inside the `docs` directory. Here is a breakdown of its components from the top down.

##### 1. The Root Level (`docs/`)

This is the top level of your documentation.

- **`index.md`**: The main homepage for your entire collection of notes.
- **`tags.md`**: The global tag index page, which automatically lists all tags used across every semester and course.
- **`assets/`**: A central folder for global resources like images, icons (`RT Logo.png`), or PDFs that might be used across multiple pages.
- **`_TEMPLATES/`**: (Recommended) A special folder, prefixed with an underscore, that holds your reusable templates for semesters, courses, and lectures. It is not published as part of the website.

##### 2. The Semester Level (`docs/Semester X/`)

Each semester is a top-level folder within `docs`.

- **`index.md`**: The overview or "dashboard" page for that specific semester. It should contain links to each course offered in that semester.
- **`.nav.yml`**: A small configuration file that controls the **order of courses** in the navigation sidebar for that semester. It ensures courses appear in a logical sequence.

##### 3. The Course Level (`docs/Semester X/COURSE_CODE/`)

Each course is a folder inside its respective semester folder. The folder name should be the course code (e.g., `CL 409`).

- **`index.md`**: The overview page for the course. This is where you should list the syllabus, instructor details, and a table of contents for all lectures.
- **`.nav.yml`**: A configuration file that controls the **order of lectures** in the navigation. This is where the automation happens, as it can automatically find and sort all lecture files.
- **`lecture-XX.md`**: Individual lecture notes. Using a numbered prefix (`01`, `02`, `03`) ensures they are sorted correctly by default.

---

#### Visualizing the Structure

Here is a visual representation of the complete structure:

```
docs/
├── _TEMPLATES/                 # Your reusable templates
│   └── _TEMPLATE_SEMESTER/
│       └── _TEMPLATE_COURSE/
│           ├── .nav.yml
│           ├── index.md
│           └── lecture-01.md
├── assets/                     # Global assets (images, PDFs)
│   ├── RT Logo.ico
│   └── RT Logo.png
├── index.md                    # Main homepage
├── tags.md                     # Global tag index
└── Semester 7/
    ├── index.md                # Overview page for Semester 7
    ├── .nav.yml                # Controls course order in Semester 7
    └── CL 409/
        ├── index.md            # Overview page for course CL 409
        ├── .nav.yml            # Controls lecture order in CL 409
        ├── lecture-01.md
        ├── lecture-02.md
        └── ...
```

---

### Your Scalable Workflow in Action

This structure makes managing your notes incredibly simple.

#### To add a new semester:

1.  **Copy** the `_TEMPLATE_SEMESTER` folder from `_TEMPLATES` into the `docs` directory.
2.  **Rename** it to `Semester 8`.
3.  **Edit** `docs/Semester 8/index.md` to update the title and content.

#### To add a new course to a semester:

1.  **Copy** the `_TEMPLATE_COURSE` folder from `_TEMPLATES` into `docs/Semester 8/`.
2.  **Rename** it to the new course code (e.g., `CL 461`).
3.  **Edit** the `.nav.yml` file inside `docs/Semester 8/` to add the new course to the navigation list.
4.  **Edit** the `index.md` inside `docs/Semester 8/CL 461/` to fill in the course details.

#### To add a new lecture to a course:

1.  **Create** a new file, such as `lecture-03.md`, inside the course folder (e.g., `docs/Semester 7/CL 409/`).
2.  **Write your notes.**

**You are done.** The navigation will automatically update to include the new lecture. You never have to edit a configuration file to add new lectures.

---

### Why This Structure Works

- **Scalable:** You can add hundreds of semesters, courses, and lectures without performance degradation or complex configuration.
- **Zero YAML Edits for Lectures:** The most frequent action—adding a lecture—requires no configuration changes. Just add the file.
- **Consistent:** Every course and semester has a predictable layout, making it easy for you and others to navigate.
- **Scoped Navigation:** Each `.nav.yml` file only manages its own level, preventing a single, massive, and unmanageable navigation tree.
