<template>
  <header id="header">
    <ul>
      <li><a class="active" href="#">뷰.JS</a></li>
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
</template>

<style></style>
