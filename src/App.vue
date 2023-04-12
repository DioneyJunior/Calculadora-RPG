<template>
  
  <header>
    <nav class="navbar navbar-expand-lg p-0" id="navbar">
      <div>
        <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="offcanvas"
        data-bs-target="#offcanvas"
        aria-controls="offcanvas"
        >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <button
          class="btn btn-primary"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#offcanvas"
          aria-controls="offcanvas"
          id="btn-ficha"
          >
          <i class="bi bi-person-fill"></i>
          Ficha de Personagem
        </button>
      </div>
    </div>
  </div>
</nav>
<CharacterInputs />
</header>
  </div>
<Style>
#navbar {
  position: fixed;
  top: 0;
  width: 100%;
  width: 100%;
  background-color: #484747;
  border-bottom: 5px solid #000000;
}
@media (max-width: 768px) {
  .navbar #btn-ficha {
    display: none;
  }
}
body {
  width: 100%
}

</Style>
</template>
<script>
import NavBar from './components/NavBar.vue';
export default {
  name: "App",
  components: {
    CharacterInputs
  }
};
</script>
