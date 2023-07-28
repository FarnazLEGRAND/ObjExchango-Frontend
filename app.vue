<template>
  <div>
    
    <header>

      <div id="main" class="container-fluid text-center text-dark p-3 ">
  <img id="logo-main" src="../assets/img/ObjExchango.jpg" class="img-fluid logo">
        <nav class="nav my_nav text-center " style="background-color: #FAEE3A; color: rgb(0, 0, 0);">
            <NuxtLink class="nav-link" to="/">Accueil</NuxtLink>
            <NuxtLink class="nav-link" to="/objet-list">Annonces</NuxtLink>
            <NuxtLink class="nav-link" to="/add-objet">Ajoutez une annonce</NuxtLink>
            <NuxtLink class="nav-link" to="/borrow-list">Liste emprunt</NuxtLink>     
        </nav>
        
    </div>  
  
</header>
<main>
  <NuxtPage />
</main>

<footer class="text-center text-white" style="background-color: #FAEE3A;">
   <div class="text-center text-dark p-3">
    © 2023 Copyright: Farnaz LEGRAND
  </div>
</footer>
  </div>
</template>

<style>
main{
  /* margin-top: -15px; */
  /* background-color: #8BD2D1; */
  background-color: #F3F4F4;

}
.my_nav {

    border-radius: 1px;
    height: 80px;
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: center;
}
.logo {
  
    height: 300px;
    width: 300px;
    background-color:#F3F4F4;
}
.nav-link {
    text-decoration: none;
    color: rgb(0, 0, 0);
}


</style>