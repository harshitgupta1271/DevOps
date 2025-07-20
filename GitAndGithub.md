# 🚀 Git & GitHub Setup Guide for Mac (M2/M1)

This guide explains how to install Git, set up a GitHub account, connect your local project with GitHub, and manage code changes over time.

---

## ✅ Option 1: Install Git via Homebrew (Recommended for M2/M1 Macs)

### 1. Install Homebrew (if not already installed)
 
Open Terminal and run:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

This auto-detects your Apple Silicon chip (M1/M2) and installs Homebrew.'

##  Install Git
After Homebrew is installed, run:
brew install git

## Verify Git Installation
git --version


## Setup GitHub Account with Git (First-Time Setup)
1. Create a New Local Git Repository
Navigate to your project folder and run:

git init




## 2. Configure Git with Your Info (One Time)
git config --global user.name "github userName"
git config --global user.email "github Email"



## 3. Add Files to the Staging Area
Choose any of the following commands based on what you want to stage:

git add -A             # Add all changes (new, modified, deleted)
git add filename        # Add a specific file
git add foldername      # Add a folder and its contents
git add *.java          # Add all Java files in the current directory


## 4. Commit Code to the Local Repository

git commit -m "Initial commit"


## 5. Create a GitHub Repo & Copy the URL
Create a repo named: Selenium-Hybrid-Framework

GitHub URL:
https://github.com/harshitgupta1271/Selenium-Hybrid-Framework.git

## 6. Connect Local Repo to Remote GitHub Repo (One Time)

git remote add origin https://github.com/harshitgupta1271/Selenium-Hybrid-Framework.git


## 7. Push Code to GitHub
git push origin master
You will be prompted to enter your GitHub username and a Personal Access Token (PAT).

## Generate a Personal Access Token (PAT)
Go to https://github.com/settings/tokens

Click Developer Settings > Personal Access Tokens > Tokens (classic) > Generate new token

Select:
 repo scope
Set expiration and description
Generate and copy the token
Use this token instead of your password when prompted during git push.

code will be pushed to github repo

## Daily Workflow (Second Round)
After making updates or changes, use:

git add -A
git commit -m "Second commit"
git push origin master

## Pull Latest Code from GitHub
          <repo url>
git pull https://github.com/harshitgupta1271/Selenium-Hybrid-Framework.git


## Clone a GitHub Repo to Local Machine
          <repo url>
git clone https://github.com/harshitgupta1271/Selenium-Hybrid-Framework.git

