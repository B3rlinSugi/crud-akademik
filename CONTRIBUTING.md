# Contributing to CRUD Akademik

Thank you for considering contributing!

## 🧠 Philosophy
This project focuses on **Database Integrity**. We do not rely on PHP to enforce relational logic. The MySQL schema must enforce foreign key constraints (`ON DELETE RESTRICT`, `CASCADE`).

## 💻 Coding Standards
*   **Security First:** You MUST use PDO Prepared Statements.
*   **Sanitization:** Always use `htmlspecialchars()` when outputting data to the view.

## 🔄 Pull Request Process
1. If you add new relational tables, you must provide the updated `.sql` dump highlighting the constraint choices.
2. Submit the PR against the `main` branch.
