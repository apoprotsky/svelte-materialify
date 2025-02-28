---
title: Elevation
description: Elevation helper classes allow you to control relative depth, or distance, between two surfaces along the z-axis.
keywords: elevation helper classes, elevation classes, svelte materialify elevation
related:
  - getting-started/usage/
  - styles/text-and-typography/
---

# Elevation

The elevation helpers allow you to control relative depth, or distance, between two surfaces along
the z-axis. There is a total of 25 elevation levels. You can set an element’s elevation by using
the class `elevation-{n}`, where `n` is a integer between 0-24 corresponding to the desired
elevation.

## Usage

The `elevation` helper classes allow you to assign a custom **z-depth** to any element.

<Components.Example file="elevation/elevations" />

## SCSS

You can also access the elevation helpers through SCSS mixins by including the elevation tool

```scss
@import 'sveltfy/src/styles/tools/elevation';

div {
  // $n is the depth
  $n: 2;
  @include elevation($n);
}
```
