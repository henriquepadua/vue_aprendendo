<script setup>
import axios from 'axios';
import { ref } from 'vue';

const books = ref([])

// Primeiro, busque os livros
axios.get('http://127.0.0.1:8000/api/v1/books')
    .then(response => {
        books.value = response.data;

        // Agora, crie uma lista de promessas para buscar os autores de cada livro
        const authorPromises = books.value.map(book => {
            return axios.get(`http://127.0.0.1:8000/api/v1/author/${book.author}`)
                .then(authorResponse => {
                    // Atribuir o nome do autor ao livro correto
                    book.authorDetails = {
                        first_name: authorResponse.data.first_name,
                        last_name: authorResponse.data.last_name
                    };
                });
        });

        // Aguarde todas as requisições de autores serem concluídas
        return Promise.all(authorPromises);
    })
    .then(() => {
        // Após todas as promessas resolvidas, os dados estão completos
        console.log(books.value);
    })
    .catch(error => {
        console.error(error.message);
    });
</script>

<template>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-flags.min.css">
    <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-payments.min.css">
    <link rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-vendors.min.css">

    <span class="d-none d-sm-inline" id="books">
        <h1 style="text-align: center;">Book List</h1> &nbsp &nbsp
        <a href="#/create_book" class="btn btn-primary d-none d-sm-inline-block" id="criar">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon" width="24" height="24" viewBox="0 0 24 24"
                stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                <path d="M12 5l0 14" />
                <path d="M5 12l14 0" />
            </svg>
            Create Book
        </a>
    </span>

    <div class="col-md-12 col-lg-8" >
        <div class="card" style="width: 58rem;" v-for="book in books" :key="book.id">
            <div class="card-header">
                <a href="" class="card-title">
                    <p><strong> Description_Book</strong> </p>
                </a>
                <div class="card card-md"> </div>
            </div>
            <div class="table-responsive"  >
                <table class="table card-table table-vcenter" id="items">
                    <tr>
                        <td class="w-100">
                            <p href="#" class="text-reset"> <strong> Title:</strong> {{ book.title }}</p>
                        </td>
                        <td class="text-nowrap text-secondary">
                            <strong> Author: </strong> {{ book.authorDetails['first_name'] }}, <strong> Genre: </strong>{{book.genre}}, <strong> Summary: </strong> {{ book.summary }},
                            <strong> Isbn: </strong>{{ book.isbn }}
                        </td>
                        <td class="text-nowrap">
                            <a href="" class="text-secondary">
                                <strong> Update_Book </strong>
                            </a>
                        </td>
                        <td class="text-nowrap">
                            <a href="" class="text-secondary">
                                <strong>Delete_Book </strong> </a>
                        </td>
                    </tr>
                </table>
            </div>
        </div>
    </div>
</template>

<style>
.card{
    margin-left: 100px;
    margin-right: 100px;
}

#books{
    margin-left: 100px;
}

#items{
    padding: 10px;
}
</style>