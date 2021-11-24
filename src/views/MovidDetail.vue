<template>
  <div class="container">
    <!-- header -->
    <header id="header">
      <ul>
        <li><a class="active" href="#">리액트.JS</a></li>
        <li><a href="#">영화</a></li>
        <li><a href="#">TV</a></li>
      </ul>
      <div class="search">
        <label for="search" class="sr-only"></label>
        <input
          type="search"
          id="search"
          placeholder="검색어를 입력하세요!"
          v-model="search"
        />
      </div>
    </header>
    <!-- //header -->
  </div>
  <!-- //container -->

  <section id="container">
      <div clas="poster">
      </div>
    </div>


  </section>
</template>
