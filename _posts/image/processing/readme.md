---
title: ImageProcessing_readme
published: false
---

# how it works
- UX : add skeleton -> process data -> inject data into skeleton
- use js when dropimage into `#dropzone` -> Trigger  `handleImages()`
- `handleImages()` validate file type (jpeg, png, etc) -> Trigger `displayImage()`
- `displayImage()` add image data into HTML through `addCardHTML()`

    - `displayImage()` read image dataurl through `e.src`
