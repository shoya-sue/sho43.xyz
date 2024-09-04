<template>
    <b-navbar toggleable="md" type="dark" variant="primary">
      <b-navbar-brand href="#">My Portfolio</b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#career">経歴</b-nav-item>
          <b-nav-item href="#projects">プロジェクト</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </template>
  
  <script>
  export default {
    name: 'HeaderSp',
  };
  </script>
  
  <style scoped>
  b-navbar {
    padding: 0.5rem 1rem;
  }
  </style>
  