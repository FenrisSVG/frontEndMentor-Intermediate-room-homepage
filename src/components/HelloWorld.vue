<script>
  export default {
    name: 'HelloWorld',
    methods: {
      showMenu(e){
        const nav = document.getElementById('nav')

        if(e.target.classList.contains('menu') || e.target.classList.contains('menu__image'))
        nav.classList.add('nav--show')
      },
      hideMenu(e){
        if(e.target.classList.contains('nav-close') || e.target.classList.contains('icon-close'))
        nav.classList.remove('nav--show')
      },
      slider(){
          const prev = document.getElementById('icon-left')
          const next = document.getElementById('icon-right')
          const sections = Array.from(document.querySelectorAll('.section'))

          let cont = 0;

          if(prev){
              prev.addEventListener('click',()=> setClass('prev'))
          }

          if(next){
              next.addEventListener('click',()=> setClass('next'))
          }

          const setClass = (direction)=>{
              sections.map(section => section.classList.remove('section--show'))
              setCont(direction);
              sections[cont].classList.add('section--show')
          }

          const setCont = (direction) =>{
              if(direction =='next'){
                  if(cont == sections.length - 1 ) cont = 0
                  else cont++
              }else{
                  if(cont == 0) cont = sections.length - 1
                  else cont--
              }
          }
      }
    },
    mounted(){
      return this.slider()
    }
  }
</script>

<template>
  <main class="main">
    <header class="header">
    <div class="header-container">
      <div class="menu" @click="showMenu">
        <img class="menu__image" src="../assets/icon-hamburger.svg" alt="">
      </div>
      <h1 class="title">room</h1>
    </div>
    <nav class="nav" id="nav">
      <div class="nav-close" @click="hideMenu">
        <img src="../assets/icon-close.svg" alt="" class="icon-close">
      </div>
      <ul class="main-menu">
        <li class="main-menu__item">home</li>
        <li class="main-menu__item">shop</li>
        <li class="main-menu__item">about</li>
        <li class="main-menu__item">contact</li>
      </ul>
    </nav>
  </header>
  <article class="article">
  <section class="section section--show">
    <header class="section-header">
      <div class="section-header__img">
        <img src="../desktop/desktop-image-hero-1.jpg" 
        loading="lazy" alt="room white chair three on a table" 
        srcset="../assets/desktop-image-hero-1.jpg,
        ../assets/mobile-image-hero-1.jpg 2x">
      </div>
    </header>
    <div class="section-body">
      <div class="section-body__text">
        <h2 class="section-body__title">Discover innovative ways to decorate</h2>
        <p class="section-body__description">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Unde, sint? Voluptate repellendus, nulla necessitatibus cum inventore quod eius neque nesciunt.</p>
      </div>
      <div class="section-body__button">
        <button class="section-button">SHOP NOW</button>
        <img src="../assets/icon-arrow.svg" alt="">
      </div>
    </div>
  </section>
  <section class="section">
    <header class="section-header">
      <div class="section-header__img">
        <img src="../desktop/desktop-image-hero-2.jpg" 
        loading="lazy" alt="room white chair three on a table" 
        srcset="../assets/desktop-image-hero-2.jpg,
        ../assets/mobile-image-hero-2.jpg 2x">
      </div>
    </header>
    <div class="section-body">
      <div class="section-body__text">
        <h2 class="section-body__title">We are available all across the globe.</h2>
        <p class="section-body__description">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Unde, sint? Voluptate repellendus, nulla necessitatibus cum inventore quod eius neque nesciunt.</p>
      </div>
      <div class="section-body__button">
        <button class="section-button">SHOP NOW</button>
        <img src="../assets/icon-arrow.svg" alt="">
      </div>
    </div>
  </section>
  <section class="section">
    <header class="section-header">
      <div class="section-header__img">
        <img src="../desktop/desktop-image-hero-3.jpg" 
        loading="lazy" alt="room white chair three on a table" 
        srcset="../assets/desktop-image-hero-3.jpg,
        ../assets/mobile-image-hero-3.jpg 2x">
      </div>
    </header>
    <div class="section-body">
      <div class="section-body__text">
        <h2 class="section-body__title">Manufactured with the best materials.</h2>
        <p class="section-body__description">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Unde, sint? Voluptate repellendus, nulla necessitatibus cum inventore quod eius neque nesciunt.</p>
      </div>
      <div class="section-body__button">
        <button class="section-button">SHOP NOW</button>
        <img src="../assets/icon-arrow.svg" alt="">
      </div>
    </div>
  </section>
  <div class="controls">
    <div class="controls-img"  id="icon-left">
      <img src="../assets/icon-angle-left.svg" alt="arrow left" loading="lazy">
    </div>
    <div class="controls-img" id="icon-right">
      <img src="../assets/icon-angle-right.svg" alt="arrow right" loading="lazy">
    </div>
  </div>
  <footer class="section-footer">
    <div class="section-footer__img">
      <img class="section-image" src="../assets/image-about-dark.jpg" alt="">
    </div>
    <div class="section-footer__text">
      <h3>About our furniture</h3>
      <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. A, dolore aut vero at nulla, ducimus corporis beatae in repellendus rem, laboriosam sunt placeat repudiandae reprehenderit?</p>
    </div>
    <div class="section-footer__img">
      <img class="section-image" src="../assets/image-about-light.jpg" alt="">
    </div>
  </footer>
  </article>
  </main>
</template>
