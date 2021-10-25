---
layout: post
title: Jesienny Stan Wyjątkowy
categories: post
custom_css: gridGallery6
---
<style>
  .gallery {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    grid-template-rows: repeat(12, 5vw);
    grid-gap: 5px;
    background-color: gray;
}

.gallery__img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.gallery__item--1 {
    grid-column-start: 1;
    grid-column-end: 7;
    grid-row-start: 1;
    grid-row-end: 5;
}

.gallery__item--2 {
    grid-column-start: 1;
    grid-column-end: 4;
    grid-row-start: 5;
    grid-row-end: 9;
}

.gallery__item--4 {
    grid-column-start: 7;
    grid-column-end: 9;
    grid-row-start: 1;
    grid-row-end: 9;

}

.gallery__item--3 {
      
    grid-column-start: 4;
    grid-column-end: 7;
    grid-row-start: 5;
    grid-row-end: 9;
}

.gallery__item--5 {
    grid-column-start: 1;
    grid-column-end: 5;
    grid-row-start: 9;
    grid-row-end: 12;

}

.gallery__item--6 {
    grid-column-start: 5;
    grid-column-end: 9;
    grid-row-start: 9;
    grid-row-end: 12;

}

</style>

<h1>Jesienny Stan Wyjątkowy</h1>

<div class="gallery">
      <figure class="gallery__item gallery__item--1">
        <img src="/assets/SAM_2147.JPG" class="gallery__img" alt="Image 1">
      </figure>
      <figure class="gallery__item gallery__item--2">
        <img src="/assets/SAM_2154.JPG" class="gallery__img" alt="Image 2">
      </figure>
      <figure class="gallery__item gallery__item--3">
        <img src="/assets/SAM_2161.JPG" class="gallery__img" alt="Image 3">
      </figure>
      <figure class="gallery__item gallery__item--4">
        <img src="/assets/SAM_2156.JPG" class="gallery__img" alt="Image 4">
      </figure>
      <figure class="gallery__item gallery__item--5">
        <img src="/assets/SAM_2142.JPG" class="gallery__img" alt="Image 5">
      </figure>
      <figure class="gallery__item gallery__item--6">
        <img src="/assets/SAM_2145.JPG" class="gallery__img" alt="Image 6">
      </figure>
    </div>
