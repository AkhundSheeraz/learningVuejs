<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark bb">
    <div class="container-fluid">
      <a class="navbar-brand" href="#/">?</a>
      <!-- <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button> -->
      <div class="collapse navbar-collapse f-grow" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link exact-active-class="active" class="nav-link anchor" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link exact-active-class="active" class="nav-link anchor" to="/about">About</router-link>
          </li>
          <li class="nav-item">
            <!-- <button type="button" class="btn btn-dark mx-1" data-bs-toggle="modal" data-bs-target="#exampleModal1">Log-In</button> -->
          <a class="nav-link" data-bs-toggle="modal" data-bs-target="#exampleModal1">Login</a>
          </li>
          <li class="nav-item dropdown">
            <a
              class="nav-link dropdown-toggle"
              href="#"
              id="navbarDropdown"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              Dropdown
            </a>
            <ul
              class="dropdown-menu ddposchange"
              aria-labelledby="navbarDropdown"
            >
              <li><a class="dropdown-item" href="#">Action</a></li>
              <li><a class="dropdown-item" href="#">Another action</a></li>
              <li><hr class="dropdown-divider" /></li>
              <li><a class="dropdown-item" href="#">Something else here</a></li>
            </ul>
          </li>
          
        </ul>
        <!-- <form class="d-flex">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <button class="btn btn-outline-primary" type="submit">Search</button>
      </form> -->
      </div>
    </div>
  </nav>
</template>

<script>
export default {
 
};
</script>

<style scoped>
.f-grow {
  flex-grow: 0;
}

.ddposchange {
  left: -75px !important;
}

.bb {
  background-color: #000912 !important;
  border-bottom: #4a8181 2px solid;
}
</style>
