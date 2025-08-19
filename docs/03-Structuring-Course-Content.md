# A Guide to Structuring Course Content

The key to a maintainable and consistent set of notes is to map the unstructured information from your course portal into a standardized format. This process involves extracting specific details and placing them into predefined fields within your templates.

There are three core templates you will be working with:

1.  **Semester Overview**
2.  **Course Overview**
3.  **Lecture Note**

#### The Mapping Process

This section details how to extract information from your source data (the course lists and descriptions you provided) and map it to the fields in your templates.

##### 1. Mapping to the Course Overview Template

This is the central hub for a single course. You will populate it by finding the corresponding data from your institute's course information.

| Template Field       | Source Data Field                      | Example (for CL 409)                 |
| :------------------- | :------------------------------------- | :----------------------------------- |
| `[COURSE_CODE]`      | `Course Code`                          | `CL 409`                             |
| `[Course Title]`     | `Course Name`                          | `Material Science`                   |
| `tags:`              | Derived from Course Name & Description | `Material Science`, `Atomic Bonding` |
| `Instructor(s):`     | `Instructor(s)`                        | `J.F. Shackelford`                   |
| `Total Credits:`     | `Total Credits`                        | `6.0`                                |
| `Type:`              | `Type`                                 | `Theory`                             |
| `Text & References:` | `Text Reference`                       | _(Copy-paste the list of books)_     |

##### 2. Mapping to the Lecture Note Template

This template is for your individual lecture notes, which you create from video transcripts. The metadata here is mostly defined by you.

| Template Field     | Source Data Field            | Example (for CL 409, Lecture 1)         |
| :----------------- | :--------------------------- | :-------------------------------------- |
| `[LECTURE_NUMBER]` | (Your own numbering)         | `1`                                     |
| `[Lecture Title]`  | (From your transcript)       | `Atomic Bonding & Crystal Structure`    |
| `date:`            | (Date of lecture or writing) | `2025-08-20`                            |
| `tags:`            | (Main topics of the lecture) | `Material Science`, `Atomic Bonding`    |
| Main Content       | (Your transcribed notes)     | _(Your detailed notes, examples, etc.)_ |

---

#### A Practical Walkthrough: Creating a Page for `CL 464`

Let's use your provided data for **CL 464 - Process Safety and Risk Management** to demonstrate the process.

**Step 1: Identify the Source Data**

From your course details, we extract the following for `CL 464`:

- **Course Code:** `CL 464`
- **Course Name:** `Process Safety and Risk Management`
- **Total Credits:** `6.0`
- **Type:** `Theory`
- **Instructors:** `Prof. Sandip Roy` (and others)
- **References:** `Daniel A. Crowl, Joseph F. Louvar...`
- **Description:** `Basic Concepts of Process Hazards...`

**Step 2: Fill the Course Overview Template**

Using the data above, you would fill in your `Course Overview` template to look like this:

```markdown
---
title: "CL 464: Process Safety and Risk Management"
tags:
  - Semester 7
  - Process Safety
  - Risk Management
---

# 📘 CL 464: Process Safety and Risk Management

Welcome to **CL 464**. This page serves as an overview — use it to navigate to lectures, see references, and explore related topics.

---

## 🗂️ Course Details

- **Total Credits:** 6.0
- **Type:** Theory
- **Instructor(s):** Prof. Sandip Roy

---

## 📝 Lecture Notes

- [Lecture 1: Basic Concepts of Process Hazards](lecture-01.md)
- ...

---

## 📚 Text & References

1.  Daniel A. Crowl, Joseph F. Louvar, _Chemical Process Safety: Fundamentals with Applications_, Prentice Hall, 2011.
2.  F.P. Lees, _Loss Prevention in Process Industries_, Vols. 1 and 2, Butterworth, 1983.
```

**Step 3: Fill the Lecture Note Template**

Next, you would create the first lecture file (`lecture-01.md`) based on your transcript for that topic.

```markdown
---
title: "Lecture 1: Basic Concepts of Process Hazards"
date: 2025-08-21
tags:
  - Process Safety
  - Hazards
  - Risk
---

# Lecture 1: Basic Concepts of Process Hazards

<!-- prettier-ignore -->
!!! abstract "Key Concepts"
    - Understanding process hazards vs. risks.
    - Principles of safety management.

---

## What is a Hazard?

A hazard is an inherent physical or chemical characteristic of a material, system, process, or plant that has the potential for causing harm...
```

By consistently following this mapping process, you ensure that every course and lecture on your site has a uniform, predictable, and professional structure.
