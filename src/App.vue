<script setup>
import Books from './components/Books.vue'
import Authors from './components/Authors.vue'
// import Principal from './components/App.vue'
import Borrowed from './components/Bookinstance_list_borrowed.vue'
import Principal from './components/Principal.vue'
import Create_book from './components/Create_Book.vue'
import { ref, computed } from 'vue'

const routes = {
  '/': Principal,
  '/books': Books,
  '/authors': Authors,
  '/mw_borrowed': Borrowed,
  '/create_book': Create_book
}

const referenciaRota = ref(window.location.hash)

window.addEventListener('hashchange', () => {
    referenciaRota.value = window.location.hash
  });

//   // Função responsável por exibir a página específica
  const currentView = computed(() => {
    return routes[referenciaRota.value.slice(1) || '/'] || PaginaErro
  })

</script>


<template>
  <component :is="currentView"/>
  <header>
    <div class="wrapper">
      
    </div>
  </header>

  <main>
    <div class="page">
    <aside class="navbar navbar-vertical navbar-expand-sm navbar-dark">
          <div class="container-fluid">
            
              <ul class="navbar-nav pt-lg-3">
                  <li class="nav-item"> 
                    <a class="nav-link" href="#/"> 
                      <span class="nav-link-icon d-md-none d-lg-inline-block">
                        <svg xmlns="http://www.w3.org/2000/svg"  width="24"  height="24"  viewBox="0 0 24 24"  fill="none"  stroke="currentColor"  stroke-width="2"  stroke-linecap="round"  stroke-linejoin="round"  class="icon icon-tabler icons-tabler-outline icon-tabler-home"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M5 12l-2 0l9 -9l9 9l-2 0" /><path d="M5 12v7a2 2 0 0 0 2 2h10a2 2 0 0 0 2 -2v-7" /><path d="M9 21v-6a2 2 0 0 1 2 -2h2a2 2 0 0 1 2 2v6" /></svg>
                      </span>
                      <span class="nav-link-title"> 
                        Home 
                      </span> 
                    </a>
                  </li> 
                  <li class="nav-item">
                    <a class="nav-link" href="#/books" >
                      <span class="nav-link-icon d-md-none d-lg-inline-block"><!-- Download SVG icon from http://tabler-icons.io/i/checkbox -->
                        <svg  xmlns="http://www.w3.org/2000/svg"  width="24"  height="24"  viewBox="0 0 24 24"  fill="none"  stroke="currentColor"  stroke-width="2"  stroke-linecap="round"  stroke-linejoin="round"  class="icon icon-tabler icons-tabler-outline icon-tabler-book"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M3 19a9 9 0 0 1 9 0a9 9 0 0 1 9 0" /><path d="M3 6a9 9 0 0 1 9 0a9 9 0 0 1 9 0" /><path d="M3 6l0 13" /><path d="M12 6l0 13" /><path d="M21 6l0 13" /></svg>
                      </span>
                      <span class="nav-link-title">
                        All Books
                      </span>
                    </a>
                  </li>
                  <li class="nav-item"> 
                    <a class="nav-link" href="#/authors" > 
                      <span class="nav-link-icon d-md-none d-lg-inline-block">
                        <svg  xmlns="http://www.w3.org/2000/svg"  width="24"  height="24"  viewBox="0 0 24 24"  fill="none"  stroke="currentColor"  stroke-width="2"  stroke-linecap="round"  stroke-linejoin="round"  class="icon icon-tabler icons-tabler-outline icon-tabler-users"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M9 7m-4 0a4 4 0 1 0 8 0a4 4 0 1 0 -8 0" /><path d="M3 21v-2a4 4 0 0 1 4 -4h4a4 4 0 0 1 4 4v2" /><path d="M16 3.13a4 4 0 0 1 0 7.75" /><path d="M21 21v-2a4 4 0 0 0 -3 -3.85" /></svg> 
                      </span>
                      <span class="nav-link-title"> 
                        All authors 
                      </span> 
                    </a>
                  </li> 
                  <li class="nav-item">
                    <a class="nav-link" href="#/mw_borrowed" >
                      <span class="nav-link-icon d-md-none d-lg-inline-block"><!-- Download SVG icon from http://tabler-icons.io/i/checkbox -->
                        <svg  xmlns="http://www.w3.org/2000/svg"  width="24"  height="24"  viewBox="0 0 24 24"  fill="none"  stroke="currentColor"  stroke-width="2"  stroke-linecap="round"  stroke-linejoin="round"  class="icon icon-tabler icons-tabler-outline icon-tabler-bookmarks"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M15 10v11l-5 -3l-5 3v-11a3 3 0 0 1 3 -3h4a3 3 0 0 1 3 3z" /><path d="M11 3h5a3 3 0 0 1 3 3v11" /></svg>
                      </span>
                      <span class="nav-link-title">
                        My Borrowed
                      </span>
                    </a>
                  </li>
              </ul>
            </div>
        </aside>
        
        <div class="page-wrapper">
          <div class="container-xl">
            <div class="page-header d-print-none">
              <div class="row align-items-center">
                <div class="col">
                  <h2 class="page-title">
                  </h2>
                </div>
              </div>
            </div>

            <div class="page-body">
              <div class="container-xl">
              </div>
            </div>
          </div>
        </div>
      </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
