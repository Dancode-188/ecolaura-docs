# 🌳 Ecolaura Git Workflow: Cultivating Clean Code



Welcome to Ecolaura's Git Workflow documentation! Just as we nurture sustainable practices in e-commerce, we cultivate a healthy, organized codebase through thoughtful Git workflows. Let's explore how we grow and maintain our digital forest! 🌿💻



## 🎯 Overview



Our Git workflow aims to:

1. Maintain a clean, organized codebase

2. Facilitate collaboration among team members

3. Ensure code quality through proper review processes

4. Enable rapid, safe deployment of new features

5. Provide clear history and easy rollback capabilities



## 🌿 Branch Strategy



We follow a modified Git Flow strategy:



- `main`: Production-ready code

- `develop`: Integration branch for features

- `feature/*`: New features or enhancements

- `bugfix/*`: Bug fixes

- `hotfix/*`: Urgent fixes for production

- `release/*`: Preparation for new product release



```mermaid

gitGraph

  commit

  branch develop

  commit

  branch feature/eco-score

  commit

  commit

  checkout develop

  merge feature/eco-score

  branch release/v1.1

  commit

  checkout main

  merge release/v1.1

  branch hotfix/urgent-fix

  commit

  checkout main

  merge hotfix/urgent-fix

  checkout develop

  merge hotfix/urgent-fix

```



## 🏷️ Branch Naming Conventions



- Feature branches: `feature/short-description`

- Bug fix branches: `bugfix/issue-number-short-description`

- Hotfix branches: `hotfix/issue-number-short-description`

- Release branches: `release/vX.Y.Z`



Examples:

- `feature/carbon-footprint-calculator`

- `bugfix/123-fix-checkout-process`

- `hotfix/456-critical-security-patch`

- `release/v1.2.0`



## 💬 Commit Message Guidelines



We follow the Conventional Commits specification:



```

<type>[optional scope]: <description>



[optional body]



[optional footer(s)]

```



Types:

- `feat`: New feature

- `fix`: Bug fix

- `docs`: Documentation only changes

- `style`: Changes that do not affect the meaning of the code

- `refactor`: Code change that neither fixes a bug nor adds a feature

- `perf`: Code change that improves performance

- `test`: Adding missing tests or correcting existing tests

- `chore`: Changes to the build process or auxiliary tools



Examples:

```

feat(product): add sustainability score to product page



The sustainability score helps users make eco-friendly choices.



Closes #234

```



```

fix(checkout): resolve issue with payment processing



Addresses a race condition in the payment gateway integration.



Fixes #567

```



## 🔄 Pull Request Process



1. Create a new branch from `develop` (for features/bugfixes) or `main` (for hotfixes)

2. Make your changes, committing regularly with meaningful commit messages

3. Push your branch to the remote repository

4. Open a Pull Request (PR) to merge your branch into `develop` (or `main` for hotfixes)

5. Fill out the PR template, including:

  - Description of changes

  - Related issue numbers

  - Screenshots (if applicable)

  - Checklist of completed items

6. Request reviews from at least two team members

7. Address any feedback and make necessary changes

8. Once approved, merge the PR using the squash and merge strategy



## 👀 Code Review Guidelines



- Review code within 24 hours of PR submission

- Look for adherence to coding standards

- Check for potential bugs or security issues

- Ensure proper test coverage

- Provide constructive feedback

- Approve only when all concerns are addressed



## 🔀 Merging Strategies



- Feature/Bugfix branches into `develop`: Squash and merge

- `release` branches into `main` and `develop`: Merge commit

- `hotfix` branches into `main` and `develop`: Merge commit



## 🚨 Handling Hotfixes



1. Create a `hotfix` branch from `main`

2. Make the necessary fixes

3. Open a PR to merge into `main`

4. After merging, immediately open another PR to merge into `develop`



## 🏷️ Release Tagging and Versioning



We use Semantic Versioning (SemVer):



- Major version: Incompatible API changes

- Minor version: Backwards-compatible new features

- Patch version: Backwards-compatible bug fixes



To create a new release:

1. Create a `release` branch from `develop`

2. Update version numbers in relevant files

3. Create a PR to merge into `main`

4. Once merged, tag the merge commit in `main`:

 ```

  git tag -a v1.2.3 -m "Release version 1.2.3"

  git push origin v1.2.3

 ```



## 🪝 Git Hooks



We use pre-commit hooks to ensure code quality:



- Lint checks

- Code formatting

- Unit test execution



Install the hooks:

```bash

pip install pre-commit

pre-commit install

```



## 🗃️ Handling Large Files



For large binary files, we use Git LFS (Large File Storage):



```bash

git lfs track "*.psd"

git add .gitattributes

```



## 💡 Best Practices



1. Rebase your branch on `develop` regularly to minimize merge conflicts

2. Keep commits atomic and focused on a single change

3. Use `git rebase -i` to clean up commits before opening a PR

4. Never force push to `main` or `develop`

5. Delete branches after merging



## 🌱 Continuous Improvement



We regularly review and refine our Git workflow:



1. Collect feedback from team members

2. Analyze pain points in the development process

3. Stay updated on Git best practices and new features

4. Adjust workflows to accommodate project growth



## 🐛 Troubleshooting



1. **Merge Conflicts**: Communicate with the team and resolve conflicts carefully

2. **Accidental Commits**: Use `git rese\` or `git revert` to undo changes

3. **Large Repository**: Regularly clean up old branches and use `git gc`



## 🤝 Contributing



Help us refine our Git practices:



1. **Workflow Improvements**: Suggest enhancements to our branching strategy

2. **Automation**: Develop scripts or tools to streamline Git operations

3. **Documentation**: Help keep this guide up-to-date and beginner-friendly



Remember, a well-maintained Git workflow is like a thriving ecosystem, fostering collaboration and nurturing the growth of our sustainable e-commerce platform. Let's commit to clean code and green practices! 🌿🔄🌍