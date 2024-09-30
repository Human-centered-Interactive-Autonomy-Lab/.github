# HIA Lab GitHub Guide

Welcome to the Human-centered Interactive Autonomy Lab (HIA Lab) GitHub repository. This guide outlines our lab's practices for version control, data handling, and collaboration.

## Git Workflow

### Cloning the Repository

To get started with a project, clone the repository:

```bash
git clone https://github.com/Human-centered-Interactive-Autonomy-Lab/[project-name].git
cd [project-name]
```

### Branching Strategy

1. Always create a new branch for your work:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. Regularly commit your changes:
   ```bash
   git add .
   git commit -m "Descriptive message about your changes"
   ```

3. Push your branch to the remote repository:
   ```bash
   git push origin feature/your-feature-name
   ```

4. Create a pull request on GitHub for review before merging into the main branch.

### Keeping Your Branch Updated

Regularly update your branch with changes from the main branch:

```bash
git checkout main
git pull origin main
git checkout your-branch-name
git merge main
```

## Sensitive Data Handling

Our lab deals with sensitive data that must be protected. Follow these guidelines:

1. Never commit sensitive data to the repository.
2. Store sensitive data in a secure, shared location (e.g., Box).
3. Use `.gitignore` to prevent accidental commits of sensitive files.
4. Use environment variables or configuration files (not tracked by Git) to store paths to sensitive data.

## Data Access and Directory Management

### Setting Up Data Access

1. Data is stored in our shared Box folder. Ensure you have access to:
   ```
   ~/Library/CloudStorage/Box-Box/Human_AGV_project/
   ```

2. In your Python scripts, use this pattern to access data:

   ```python
   import os
   
   box_path = os.path.expanduser("~/Library/CloudStorage/Box-Box/Human_AGV_project/ISU_Modeling/Code")
   file_path = os.path.join(box_path, "dataset_name.csv")
   ```

3. Adjust the path as necessary for different projects or datasets.

### Directory Structure

Maintain a consistent directory structure across projects:

```
project-name/
│
├── data/
│   └── (symlink to Box folder or .gitignore this directory)
├── notebooks/
├── src/
├── tests/
├── README.md
└── requirements.txt
```

## Best Practices

1. Always pull before starting work: `git pull origin main`
2. Regularly push your changes to backup your work.
3. Use meaningful commit messages.
4. Review code before creating a pull request.
5. Communicate with team members about significant changes.
6. Keep documentation and comments up-to-date.

## Troubleshooting

If you encounter issues:

1. Check the project-specific guide if available.
2. Consult with team members.
3. For Git-related problems, refer to the [Git documentation](https://git-scm.com/doc).

## Contact

For questions or assistance, contact:
- Lab Director: Jundi Liu (jundiliu@iastate.edu)
- GitHub Administrator: Mobina Amrollahi (mobinaa@iastate.edu)
