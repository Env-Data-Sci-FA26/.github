# Git, GitHub, and RStudio Setup Guide

This guide walks you through setting up Git, GitHub, and connecting them to RStudio. We draw from [Happy Git and GitHub for the useR](https://happygitwithr.com/) — a great resource to bookmark for deeper reference.

---

> [!NOTE]
> **Shell vs. R: Know Where You're Running Code**
>
> Throughout these steps, some instructions ask you to run code in **R** (in the RStudio Console), and others ask you to run code in the **shell**. Pay close attention to which is which — they are different environments and the commands are not interchangeable.
>
> The **shell** (also called the terminal, command line, or command prompt) is a text-based interface for talking directly to your operating system — separate from R entirely. Here's how to open one on your computer:
> - **Mac:** Open the **Terminal** app (find it via Spotlight search or in Applications → Utilities → Terminal)
> - **Windows:** Open **Git Bash** (installed with Git in Step 1 below; search for it in your Start menu)
>
> Alternatively, RStudio has a built-in shell you can use without ever leaving the IDE: just click the **Terminal** tab in the lower-left pane of RStudio, right next to the Console tab. This is often the most convenient option and works on Mac and Windows alike.

---

## Step 1: Create a GitHub Account

If you don't already have one, create a free account at [github.com](https://github.com). Follow [Chapter 5](https://happygitwithr.com/github-acct) for tips on choosing a username.

---

## Step 2: Install Git

Follow [Chapter 4](https://happygitwithr.com/install-git) of Happy Git to install Git on your operating system.

---

## Step 3: Install R and RStudio

Make sure you have current versions of both R and RStudio installed. See [Chapter 6](https://happygitwithr.com/install-r-rstudio) for guidance.

---

## Step 4: Configure Git

In RStudio, introduce yourself to Git by running the following R code:

```r
install.packages("usethis") #only do this ONCE
library(usethis)
use_git_config(user.name = "Your Name", user.email = "your@email.com")
```

Use the email associated with your GitHub account. See [Chapter 7](https://happygitwithr.com/hello-git) if you want more detail.

---

## Step 5: Create a Personal Access Token (PAT)

GitHub uses PATs instead of passwords for authentication. Run the following in R:

```r
usethis::create_github_token()
```

This opens GitHub in your browser. When setting up your token:
- Give it a memorable name (e.g., the current date)
- Change the **Expiration** to **"No expiration"**
- Keep all other default settings
- Click **Generate token** and **copy it immediately** — you won't be able to view it again

Then store your token in R:

```r
install.packages("gitcreds") #only do this ONCE
gitcreds::gitcreds_set()
```

Paste your token when prompted. **Your token should begin with 'ghp' followed by a long string of numbers and letters**. See [Chapter 9](https://happygitwithr.com/https-pat) for more detail. We use **HTTPS (not SSH)** for this course.

---

## Step 6: Connect RStudio to GitHub

Verify everything is connected by following [Chapter 11](https://happygitwithr.com/rstudio-git-github) — you'll create a test repo on GitHub and clone it into RStudio to confirm the integration works.

---

## Step 7 (Optional): Set Up Two-Factor Authentication

GitHub recommends enabling 2FA. You can use the **DUO app** (same one used for CSU logins):

1. Go to: [GitHub 2FA setup](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)
2. Follow the instructions for **"using a TOTP app"**
3. Select DUO as your authenticator app

---

## Troubleshooting

If you run into issues, [Chapters 13 and 14](https://happygitwithr.com/troubleshooting) of Happy Git cover the most common problems and fixes.
