---
title: 'Container'
order: 2
---

> the container define the main content width as well as the minimum negative space between the horizontal edges of the screen and the content.

## Default container

the default container follow those rules :

- When viewport width **< 576px (m)**, the default container have **16px (1mu)** paddings.
- When viewport width **>= 576px (m)**, the default container have **32px (2mu)** paddings.
- When viewport width **< 1376px**, the default container is **fluid**.
- When viewport width **>= 1376px**, the default container is **1376px (86mu)** wide, given the paddings, this mean that inside **usable width is equal to 1312px (82mu)**

<small>Reminder : mu = MagicUnit. Ex: 3.5mu = MagicUnit \* 3.5</small>

## The fluid container

the fluid container uses the same paddings values but is fluid at any viewport width.

### Related docs :

See also [the grid documentations](/Foundations/Layout/Grid/)