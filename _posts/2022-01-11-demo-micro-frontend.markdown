---
layout: post
title: Micro Frontends
description: Concept and implement a micro frontends application
date: 2022-01-11 10:59:00 +0700
categories: platform
thumbnail: https://lh3.googleusercontent.com/pw/AL9nZEUGu3_fnvmDeMQ5fVxRUxS_vKOzKJuCeWhFDEVXWX8vsy_hKyEzHrnJgYwl9Nmw0ChKE0S2rcs4Kh3gHUKtYzIgE6eTjBOTOz33OovTDJf6DDgJ_0gjDwLTJuJ-6wGwdMU153imSmafR11tKRXPzp-vOw=w1692-h969-no
---

![](https://lh3.googleusercontent.com/pw/AL9nZEUGu3_fnvmDeMQ5fVxRUxS_vKOzKJuCeWhFDEVXWX8vsy_hKyEzHrnJgYwl9Nmw0ChKE0S2rcs4Kh3gHUKtYzIgE6eTjBOTOz33OovTDJf6DDgJ_0gjDwLTJuJ-6wGwdMU153imSmafR11tKRXPzp-vOw=w1692-h969-no)

Micro Frontends

### Keyword
- Micro frontends

### Concept
The idea behind Micro Frontends is to think about a website or web app as a composition of features which are owned by independent teams. Each team has a distinct area of business or mission it cares about and specialises in. A team is cross functional and develops its features end-to-end, from database to user interface. (micro-frontends.org)

### Demo
Create a repository master-app as a frame with navigation menu link to features, 2 repositories for development feature of each Team 1 and Team 2, a repository config-app help configuration micro frontends use [Single-spa](https://single-spa.js.org/docs/getting-started-overview) framework.

### Repositories
- Master app: https://github.com/duycs/demo-micro-frontends
- Config app: https://github.com/duycs/demo-micro-frontends-root-config.git
- App developed by Team 1: https://github.com/duycs/demo-micro-frontends-app-team-1.git
- App developed by Team 2: https://github.com/duycs/demo-micro-frontends-app-team-2.git

### References
- https://micro-frontends.org/
- https://single-spa.js.org/
- https://qiankun.umijs.org/
- https://luigi-project.io/
- https://www.freecodecamp.org/news/developing-and-deploying-micro-frontends-with-single-spa/
