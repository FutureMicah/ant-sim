# Pushing this to GitHub

## 1. Create the repo on GitHub first

In the browser: New repository, do NOT initialise with a README. Copy the URL.

## 2. Local

git init
git add .
git commit -m "the hole: ant colony survival game"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main

## With GitHub CLI instead

gh repo create the-hole --public --source=. --push

## 3. Optional: Pages

Settings, Pages, Source: Deploy from a branch, Branch: main, Folder: / (root).
The game then runs at https://<you>.github.io/<repo>/

## Notes

- Rename the folder to the-hole first.
- Replace <YOUR NAME> in LICENSE.
- Nothing here needs npm, a bundler, or CI.
