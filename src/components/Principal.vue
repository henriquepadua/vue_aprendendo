<template>
    <head>
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler.min.css">
        <link rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-flags.min.css">
        <link rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-payments.min.css">
        <link rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-vendors.min.css">
    </head>
    <main>
        <div class="dropdown">
            <h2 style="text-align: center;">Dynamic content</h2>

            <p style="text-align: center;">The library has the following record counts:</p>
            <div class="table-responsive" id="tabela">
                <div class="col-3">
                    <div class="row row-cards">
                        <div class="col-sm-3 col-lg-3">
                            <div class="card card-sm">
                                <div class="card-body">
                                    <div class="row align-items-center">
                                        <div class="col-auto">
                                            <span class="bg-primary text-white avatar">
                                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24"
                                                    viewBox="0 0 24 24" fill="none" stroke="currentColor"
                                                    stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                                                    class="icon icon-tabler icons-tabler-outline icon-tabler-book">
                                                    <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                                                    <path d="M3 19a9 9 0 0 1 9 0a9 9 0 0 1 9 0" />
                                                    <path d="M3 6a9 9 0 0 1 9 0a9 9 0 0 1 9 0" />
                                                    <path d="M3 6l0 13" />
                                                    <path d="M12 6l0 13" />
                                                    <path d="M21 6l0 13" />
                                                </svg>
                                            </span>
                                        </div>
                                        <div class="col">
                                            <div class="font-weight-medium">
                                                Books:
                                            </div>
                                            <div class="text-secondary">
                                                {{ num_books }}
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="col-sm-6 col-lg-3">
                            <div class="card card-sm">
                                <div class="card-body">
                                    <div class="row align-items-center">
                                        <div class="col-auto">
                                            <span class="bg-primary text-white avatar">
                                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24"
                                                    viewBox="0 0 24 24" fill="none" stroke="currentColor"
                                                    stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                                                    class="icon icon-tabler icons-tabler-outline icon-tabler-book">
                                                    <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                                                    <path d="M3 19a9 9 0 0 1 9 0a9 9 0 0 1 9 0" />
                                                    <path d="M3 6a9 9 0 0 1 9 0a9 9 0 0 1 9 0" />
                                                    <path d="M3 6l0 13" />
                                                    <path d="M12 6l0 13" />
                                                    <path d="M21 6l0 13" />
                                                </svg>
                                            </span>
                                        </div>
                                        <div class="col">
                                            <div class="font-weight-medium">
                                                Copies:
                                            </div>
                                            <div class="text-secondary">
                                              {{ num_copies }}
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="col-sm-6 col-lg-3">
                            <div class="card card-sm">
                                <div class="card-body">
                                    <div class="row align-items-center">
                                        <div class="col-auto">
                                            <span class="bg-primary text-white avatar">
                                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24"
                                                    viewBox="0 0 24 24" fill="none" stroke="currentColor"
                                                    stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                                                    class="icon icon-tabler icons-tabler-outline icon-tabler-book">
                                                    <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                                                    <path d="M3 19a9 9 0 0 1 9 0a9 9 0 0 1 9 0" />
                                                    <path d="M3 6a9 9 0 0 1 9 0a9 9 0 0 1 9 0" />
                                                    <path d="M3 6l0 13" />
                                                    <path d="M12 6l0 13" />
                                                    <path d="M21 6l0 13" />
                                                </svg>
                                            </span>
                                        </div>
                                        <div class="col">
                                            <div class="font-weight-medium">
                                                Copies available:
                                            </div>
                                            <div class="text-secondary">
                                                {{ num_instances_available }}
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="col-sm-6 col-lg-3">
                            <div class="card card-sm">
                                <div class="card-body">
                                    <div class="row align-items-center">
                                        <div class="col-auto">
                                            <span class="bg-primary text-white avatar">
                                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24"
                                                    viewBox="0 0 24 24" fill="none" stroke="currentColor"
                                                    stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
                                                    class="icon icon-tabler icons-tabler-outline icon-tabler-users">
                                                    <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                                                    <path d="M9 7m-4 0a4 4 0 1 0 8 0a4 4 0 1 0 -8 0" />
                                                    <path d="M3 21v-2a4 4 0 0 1 4 -4h4a4 4 0 0 1 4 4v2" />
                                                    <path d="M16 3.13a4 4 0 0 1 0 7.75" />
                                                    <path d="M21 21v-2a4 4 0 0 0 -3 -3.85" />
                                                </svg>
                                            </span>
                                        </div>
                                        <div class="col">
                                            <div class="font-weight-medium">
                                                Authors:
                                            </div>
                                            <div class="text-secondary">
                                                {{ num_authors }}
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <p>
            <!-- You have visited this page {{ num_visits }}{% if num_visits == 1 %} time{%
    else %} times{% endif %}. -->
        </p>
    </main>
</template>

<script setup>

import axios from 'axios';
import { ref } from 'vue';
const books = ref([]) // Estado reativo para armazenar os livros
const num_books = ref(0) // Estado reativo para armazenar o número de livros
const num_authors = ref(0) // Estado reativo para armazenar o número total de autores
const num_copies = ref(0) // Estado reativo para armazenar o número total de autores
const num_instances_available = ref(0) // Estado reativo para armazenar o número total de emprestimos 

// Buscar livros
axios.get('http://127.0.0.1:8000/api/v1/books')
    .then(response => {
        books.value = response.data;
        num_books.value = books.value.length; // Atualiza o número de livros
    })
    .catch(error => {
        console.error(error.message);
    });

// Buscar autores
axios.get('http://127.0.0.1:8000/api/v1/author')
    .then(response => {
        num_authors.value = response.data.length; // Atualiza o número total de autores
    })
    .catch(error => {
        console.error(error.message);
    });

// Buscar instancia de livros
axios.get('http://127.0.0.1:8000/api/v1/bookinstance')
    .then(response => {
      num_copies.value = response.data.length; // Atualiza o número total de autores
    })
    .catch(error => {
        console.error(error.message);
    });

// Buscar instancia de livros
axios.get('http://127.0.0.1:8000/api/v1/bookinstance')
    .then(response =>{
      if(num_instances_available.value.status__exact == 'a'){
        num_instances_available.value = response.data.length; // Atualiza o número total de autores
      }
    })
    .catch(error => {
        console.error(error.message);
    });    

//num_instances_available
</script>

<style>

</style>