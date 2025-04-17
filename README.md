# Apply Gitflow in a realistic DevOps scenario to simulate managing a feature, a hotfix, and a release cycle

## Why Gitflow?
- Gitflow helps structure your workflow, especially in a team

- Clear separation between development and production code

- Easier collaboration with multiple contributors

- Simplifies hotfix and release cycles

- Promotes stable deployments and clean PR history



##Overview of what we would do
We're simulating a realistic Gitflow scenario with:

- A main branch (production-ready code)

- A develop branch (integration of features)

- A feature/login-page (developing a login page)

- A release/v1.0.0 (release prep work)

- A hotfix/typo-fix (urgent bug fix after release)

- Tagging the release (v1.0.0)

- Writing structured commit messages (feat:, fix:, docs:)

- Including a Gitflow Simulation section in README.md

## Step by step guide with examples
### 1. Create a Repository
We create a new repo on GitHub and named it devops-gitflow

### 2. Initialize with a Simple App
Created an index.html with basic HTML content. 

```
<!-- index.html -->
<!DOCTYPE html>
<html>
  <head>
    <title>Welcome</title>
  </head>
  <body>
    <h1>Hello World!</h1>
  </body>
</html>
```

Commit and push to main:

```
git add .
git commit -m "feat: initial commit with base HTML"
git push origin main

```

### 3. Set up develop Branch

```
git checkout -b develop
git push -u origin develop
```
<img width="1374" alt="Screenshot 2025-04-17 at 22 06 03" src="https://github.com/user-attachments/assets/0a9498d5-5507-40f6-a80c-7153a8dda824" />

**Why?** develop is where we combine all feature work before pushing to main.

### Create feature/login-page Branch

```
git checkout -b feature/login-page
```

Add a simple login form in login.html

```
<!-- login.html -->
<h2>Login Page</h2>
<form>
  <label>Username:</label><input type="text" />
  <label>Password:</label><input type="password" />
  <button>Login</button>
</form>
```

```
git add .
git commit -m "feat: add login page"
git push -u origin feature/login-page
```
<img width="1479" alt="Screenshot 2025-04-17 at 22 08 11" src="https://github.com/user-attachments/assets/0c32c9d0-fd00-4760-8bc4-f437dccbca5e" />

Create a pull request (PR) from feature/login-page → develop on GitHub and merge it.


<img width="1196" alt="Screenshot 2025-04-17 at 22 08 53" src="https://github.com/user-attachments/assets/e31fb4b0-603f-4704-9341-63a2ff1b4e57" />

<img width="1234" alt="Screenshot 2025-04-17 at 22 17 38" src="https://github.com/user-attachments/assets/223ff215-199e-4aa2-8f92-63f24a8b40bd" />

<img width="1104" alt="Screenshot 2025-04-17 at 22 18 01" src="https://github.com/user-attachments/assets/da5fb98d-5200-4b6b-97b0-22acde727b17" />

<img width="1420" alt="Screenshot 2025-04-17 at 22 18 25" src="https://github.com/user-attachments/assets/1939d02d-b962-41e6-8a0e-b130bcc62b1d" />

### 5. Create release/v1.0.0 Branch from develop

```
git checkout develop
git pull origin develop
git checkout -b release/v1.0.0
```

<img width="1345" alt="Screenshot 2025-04-17 at 22 25 15" src="https://github.com/user-attachments/assets/b0235612-653b-43b5-9e64-2c9978c610fe" />


### Make small changes — for example, update README.md:

```
echo "## v1.0.0 Release" >> README.md
git add README.md
git commit -m "docs: update README for release v1.0.0"
git push -u origin release/v1.0.0
```

<img width="1336" alt="Screenshot 2025-04-17 at 22 26 41" src="https://github.com/user-attachments/assets/64dff904-5ab5-4fdf-8188-f7c11f6499a2" />


Then, create a PR from release/v1.0.0 → main and merge it.

<img width="1347" alt="Screenshot 2025-04-17 at 22 27 13" src="https://github.com/user-attachments/assets/ff45e022-c5b6-4b54-9c28-b12eb06b22ff" />


<img width="1286" alt="Screenshot 2025-04-17 at 22 27 25" src="https://github.com/user-attachments/assets/3881acd0-8479-4f48-bac8-0d2584b7ae70" />


### 6. Tag the Release

```
git checkout main
git pull origin main
git tag -a v1.0.0 -m "Release version 1.0.0"
git push origin v1.0.0
```

### 7. Simulate a Hotfix
Now introduce a small typo in index.html on the main branch. Then create:

```
git checkout main
git checkout -b hotfix/typo-fix
```

Fix the typo. Then:

```
git add .
git commit -m "fix: correct typo in homepage"
git push -u origin hotfix/typo-fix
```

Create a PR → merge into both:

- main

- develop (so dev stays updated)

## Conclusion
This Gitflow simulation project helped demonstrate how structured branching strategies support smoother and more efficient software development. By following the Gitflow methodology, we practiced:

- Creating and merging a feature branch into the develop branch

- Preparing a release branch from develop, simulating production readiness

- Merging to main and tagging a release (v1.0.0)

- Creating a hotfix from main for an urgent bug and merging it back into both main and develop

This approach mirrors real-world development workflows, helping teams avoid confusion, minimize conflicts, and manage changes systematically.
