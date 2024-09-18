<template>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-flags.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-payments.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/core@1.0.0-beta17/dist/css/tabler-vendors.min.css">
  

  <span class="d-none d-sm-inline">
      <h1 style="text-align: center;">Book List</h1> &nbsp &nbsp
        <a href="#/create_book" class="btn btn-primary d-none d-sm-inline-block" >
          <svg xmlns="http://www.w3.org/2000/svg" class="icon" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M12 5l0 14" /><path d="M5 12l14 0" /></svg>
          Create Book
        </a>
  </span>  

  <div class="col-md-12 col-lg-8">
    <div class="card">
      <div class="card-header">
        <a href="" class ="card-title" ><p ><strong> Description_Book</strong>  </p></a> 
         <div class="card card-md"> () &nbsp &nbsp </div> 
      </div>
      <div class="table-responsive">
        <table class="table card-table table-vcenter">
          <tr>
            <td class="w-100">
              <p href="#" class="text-reset"> <strong> Title:</strong> </p>
            </td>
            <td class="text-nowrap text-secondary">
              <strong> Author: </strong> , <strong> Genre: </strong>, <strong> Summary: </strong> , <strong> Isbn: </strong>
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

  <!-- <li class="card card-sm" id="books">
      <div class="col-md-5">
      <a href="" class ="card-title" ><p> Title:</p></a> <div class="card card-md"> () &nbsp &nbsp </div>
      <a href="">Atualizar_Livro</a> &nbsp &nbsp 
      <button> <a href="">Deletar_Livro</a> </button>
      </div>
  </li>
    <div class="hr"></div>  -->
</template>

<style scoped>

</style> 
