<template>
    <b-navbar toggleable="lg" type="dark" variant="primary">
      <b-navbar-brand href="#">My Portfolio</b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item href="#career">経歴</b-nav-item>
          <b-nav-item href="#projects">プロジェクト</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </template>
  
  <script>
  export default {
    name: 'HeaderPc',
  };
  </script>
  
  <style scoped>
  b-navbar {
    padding: 1rem 2rem;
  }
  </style>
  