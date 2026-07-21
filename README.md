<div align="center">

# 🐍 GitHub Contribution Snake Setup Guide

### Add an Animated GitHub Contribution Snake to Your GitHub Profile

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=24&duration=3500&pause=1000&center=true&vCenter=true&width=900&lines=Learn+How+to+Add+an+Animated+GitHub+Snake!;Automate+Your+GitHub+Profile!;Easy+Step-by-Step+Guide!;Beginner+Friendly+%F0%9F%9A%80" />

<p>

![GitHub](https://img.shields.io/badge/GitHub-Actions-black?style=for-the-badge&logo=github)
![Workflow](https://img.shields.io/badge/Workflow-Automated-success?style=for-the-badge)
![SVG](https://img.shields.io/badge/Output-SVG-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

</p>

> Turn your GitHub contribution graph into a beautiful animated snake using **GitHub Actions**.

</div>

---

# 📑 Table of Contents

- Introduction
- Prerequisites
- Step 1 - Create a New Repository
- Step 2 - Create the Workflow
- Step 3 - Enable Write Permissions
- Step 4 - Run the Workflow
- Step 5 - Add the Snake to Your Profile
- Example
- Common Problems
- FAQ

---

# 📖 Introduction

The GitHub Contribution Snake transforms your contribution graph into an animated snake that "eats" your contributions.

Everything runs automatically using **GitHub Actions**, so after setup there is nothing else you need to do.

---

# ✅ Prerequisites

Before starting, make sure you have:

- A GitHub account
- A public GitHub profile
- Basic GitHub knowledge
- A public profile repository

---

# 🚀 Step 1: Create a New Repository

Go to **GitHub**

Click

```
New Repository
```

Name it something like

```
profilesnake
```

Make it

```
Public
```

Initialize it with

```
README.md
```

Your repository should look like

```
profilesnake
│
├── README.md
```

---

# ⚙️ Step 2: Create the Workflow

Inside the repository click

```
Add file
      ↓
Create new file
```

Create the following file

```
.github/workflows/snake.yml
```

Paste this YAML:

```yaml
name: generate snake

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: Generate GitHub contribution snake
        uses: Platane/snk@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - name: Push snake to output branch
        uses: peaceiris/actions-gh-pages@v4
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
          publish_branch: output
```

Commit the file.

---

# 🔐 Step 3: Enable Write Permissions

⚠️ This is the step many people forget.

Open your repository.

Go to

```
Settings
      ↓
Actions
      ↓
General
```

Scroll down until you see

```
Workflow permissions
```

Select

```
✅ Read and write permissions
```

Click

```
Save
```

Without enabling this permission you will receive

```
403 Permission Denied
```

---

# ▶️ Step 4: Run the Workflow

Go to

```
Actions
```

Choose

```
generate snake
```

Click

```
Run workflow
```

Wait about one minute.

GitHub will automatically create a new branch named

```
output
```

containing

```
github-contribution-grid-snake.svg

github-contribution-grid-snake-dark.svg
```

---

# ❓ How do I know if it worked?

## Step 1

Go to

```
Code
```

## Step 2

Click the branch selector

```
main ▼
```

## Step 3

Look for another branch named

```
output
```

---

## ✅ If the output branch exists

Congratulations!

Your snake animation has been generated successfully.

Proceed to **Step 5**.

---

## ❌ If the output branch does NOT exist

Go back to

```
Actions
```

Open the latest workflow run.

Expand

```
Push snake to output branch
```

Check for any errors.

The most common cause is forgetting to enable

```
Read and write permissions
```

---

# 🐍 Step 5: Add the Snake to Your GitHub Profile

Open your GitHub Profile Repository.

For example

```
YOUR_USERNAME/YOUR_USERNAME
```

If your username is

```
loganthp19-arch
```

then your repository must be

```
loganthp19-arch/loganthp19-arch
```

Edit the **README.md** and paste the following code.

```html
<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="https://raw.githubusercontent.com/YOUR-GITHUB-USERNAME/YOUR-REPO-NAME/output/github-contribution-grid-snake-dark.svg">

  <source
    media="(prefers-color-scheme: light)"
    srcset="https://raw.githubusercontent.com/YOUR-GITHUB-USERNAME/YOUR-REPO-NAME/output/github-contribution-grid-snake.svg">

  <img
    alt="GitHub contribution snake"
    src="https://raw.githubusercontent.com/YOUR-GITHUB-USERNAME/YOUR-REPO-NAME/output/github-contribution-grid-snake.svg">
</picture>
```

Commit the changes.

That's it!

Your GitHub profile will now display the animated contribution snake.

---

# 💡 Example

Suppose your GitHub username is

```
loganthp19-arch
```

Then your snake URL becomes

```
https://raw.githubusercontent.com/loganthp19-arch/profilesnake/output/github-contribution-grid-snake.svg
```

---

# 🛠 Common Problems

## ❌ 403 Permission Denied

Enable

```
Settings
↓
Actions
↓
General
↓
Read and write permissions
```

---

## ❌ 404 Not Found

Check

- Repository name
- Branch name (`output`)
- README URLs

---

## ❌ Snake Not Showing

Make sure both repositories are

- Public
- Correctly named

---

## ❌ No Output Branch

Open

```
Actions
```

Check the workflow logs for errors.

---

# ❓ Frequently Asked Questions

### Does this count as a GitHub contribution?

No.

The animation only visualizes your existing contributions.

---

### How often does it update?

Every

```
12 Hours
```

using GitHub Actions.

---

### Can I customize the snake?

Yes!

The `Platane/snk` action supports different themes and color palettes.

---

### Does it work on mobile?

Yes.

The SVG animation is fully responsive.

---

# 🎉 Congratulations

You have successfully configured the GitHub Contribution Snake.

Every 12 hours GitHub Actions will regenerate the SVG automatically, keeping your profile animation up to date without any manual work.

Happy Coding! 🚀

</div>
