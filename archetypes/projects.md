---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"
date: '{{ .Date }}'
description: "A short summary of the project."
image: "project-image.jpg"
technologies: []
github: ""
draft: true
---

## Full Description

Describe the project in detail here.

## What I Built

List the main features and components:

- Feature 1
- Feature 2

## What I Learned

Reflect on what you learned:

- Skill 1
- Skill 2

## Technologies Used

- Tech 1
- Tech 2

## Links

- [GitHub]({{ .Params.github }})

## Screenshots

Add images here.