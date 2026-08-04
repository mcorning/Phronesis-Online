---
title: Website Publishing Infrastructure
created: 2026-08-04
---

# Purpose

This note documents the architecture and workflow used to publish the Phronesis Project website.

The goal is to eliminate ambiguity about where files live, which repository is authoritative, and how changes reach the public website.

---

# Authoritative Working Copy

The authoritative working copy is:

C:\Users\mcorn\Documents\Vaults\_PUBLIC\Phronesis

This directory is simultaneously

- the Obsidian vault
- the Git working tree
- the repository used to publish the website

The vault itself contains a `.git` directory.

All future website development occurs here.

---

# Repository

Git remote:

https://github.com/mcorning/Phronesis-Online.git

Typical workflow:

git status

git add ...

git commit

git push origin main

---

# GitHub Pages

Publishing Source

Branch:
main

Folder:
/(root)

Custom Domain

phronesisproject.org

Deployment

git push
↓

GitHub repository

↓

GitHub Pages build

↓

phronesisproject.org

---

# Local Clones

A second clone exists:

C:\Users\mcorn\Documents\GitHub\Phronesis-Online

It points to the same GitHub repository.

It is no longer used for active development.

Retain it only until any unique work has been recovered.

Do not perform commits or pushes from this clone.

---

# Release Checklist

Before Push

□ review diff

□ confirm links

□ review navigation

□ commit

□ push

After Push

□ verify GitHub Pages build

□ verify website

□ test navigation

□ test browser console

□ verify mobile

Reality decides when deployment is complete.

---

# Website Principles

The vault is the source.

GitHub is publication.

GitHub Pages is deployment.

Every public page should:

- provide navigation home

- provide navigation to related pages

- provide a next action where appropriate

No page is an island.