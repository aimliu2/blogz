---
title: ImageProcessing_readme
published: false
---
# How it works
- UX : add skeleton -> process data -> inject data into skeleton -> Download

## UX : add skeleton
- `handleImages()` was trigger by `dropzone` event on `drop` or `filesInput` event on `change`
- `handleImages()` validate file type (jpeg, png, etc), then trigger `Skeleton()`
- `initSkeleton()` create both `Card` and `Modal` skeleton with some index, then trigger `processImageData()`

## process data
- `processImageData() [Promise]` wait until image blob compress resolve, then return `JSON obj.`, meta data of images
- wait until all `Promise.all(jarr.map(processImageData))` resolve, then trigger `displayImageData()` on each `JSON obj.`

## inject data into skeleton
- `displayImageData()` trigger `addCardHTML()` and `addModal()`
    - `addCardHTML()` target and inject some HTML element into DOM
    - `addModal()` target and inject some HTML element into DOM, also draw canvas from Blob

## Download
- `downloadBlobCompress()` single download. find canvas -> compress to blob at designated ratio -> download
- `downloadAll()` multi download. find all canvases -> get blob -> zip, Rely on JSZip lib -> download
    - JSZIP : - https://stuk.github.io/jszip/
    - `urlToPromise()` helper JSZip, get blob from blob url 