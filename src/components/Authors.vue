<template>
    <header>
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler.min.css">
        <link rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-flags.min.css">
        <link rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-payments.min.css">
        <link rel="stylesheet"
            href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-vendors.min.css">
    </header>

    <main>
        <span class="d-none d-sm-inline">
            <h1 style="text-align: center;">Author List</h1> &nbsp &nbsp
            <a href="" class="btn btn-primary d-none d-sm-inline-block" id="criar">
                <svg xmlns="http://www.w3.org/2000/svg" class="icon" width="24" height="24" viewBox="0 0 24 24"
                    stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none" />
                    <path d="M12 5l0 14" />
                    <path d="M5 12l14 0" />
                </svg>
                Create Author
            </a>
        </span>

        <div class="container">
            <div class="row">
                <div class="col-md-8 col-lg-6">
                    <div class="card" v-for="author in authors" :key="author.id" style="width: 58rem;">
                        <div class="card-header">
                            <a href="" class="card-title">
                                <p><strong> Description_Author</strong> </p>
                            </a>
                        </div>
                        <div class="table-responsive">
                            <table class="table card-table table-vcenter">
                                <tr>
                                    <td class="w-100">
                                        <p href="#" class="text-reset"> <strong> Fist_name:</strong>
                                            {{ author.first_name }}<strong> Last_name: </strong> {{ author.last_name }}
                                        </p>
                                    </td>
                                    <td class="text-nowrap">
                                        <a href="" class="text-secondary">
                                            <strong> Update_Author</strong>
                                        </a>
                                    </td>
                                    <td class="text-nowrap">
                                        <a href="" class="text-secondary">
                                            <strong>Delete_Author</strong> </a>
                                    </td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script setup>

import axios from 'axios';
import { ref } from 'vue';

const authors = ref([])

axios.get('http://127.0.0.1:8000/api/v1/author')
    .then(response => {

        authors.value = response.data

    })
    .catch(error => {
        console.error(error.message)
    })
</script>

<style>
#criar{
    margin-left: 680px;
    padding: 10px;
}
.card{
    margin-left: 300px;
}
.row{
    padding: 10px;
}

</style>