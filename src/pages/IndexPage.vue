<template>
  <q-page class="full-width main-background-container">
    <div class="row main-container">
      <div class="side-1 col-xs-12 col-sm-2 col-md-1">
        <div class="grey-logo">
          <q-img src="" />
        </div>
        <div class="icon-container">
          <nav>
            <div class="home"></div>
            <div class="task1"></div>
            <div class="profiles"></div>
            <div class="holder1"></div>
            <div class="holder2"></div>
            <div></div>
          </nav>
        </div>
      </div>
      <div class="side-2 row col-xs-12 col-sm-3 col-md-2">
        <div class="app-title col-12">GMS</div>
        <div class="side-menu col-grow justify-center">
          <div class="col-12 profiles">Profiles</div>
          <div class="col-12 task">Profiles</div>
          <div class="col-12 user">Profiles</div>
          <div class="col-12 user">Profiles</div>
        </div>
      </div>
      <div class="content col-xs-12 col-sm-7 col-md-9">
        .col-12 .col-md-2
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>

<!-- Style -->

<style scoped>

.main-background-container{
  background-color: rgb(237, 240, 243);
}
.main-container{
  height: 100vh;
  background-color: rgb(237, 240, 243);
}
.side-1, .side-2{
  background-color: #ffffff;
}
.side-2 .app-title{
  display: grid;
  place-items: center center;
  height: 15%;
  border-bottom: 2px solid rgb(237, 240, 243);
}
.side-2 .side-menu{
  height: 85%;
  padding: 90px 15px 0 15px;
}
.side-2 .side-menu div{
  padding: 10px 10px 10px 11%;
  border-radius: 10px;
  font-size: 1.2em;
  margin: 20px 0px
}
.side-2 .side-menu div:nth-child(2){
  background-color: #f2f5f7;
}
.side-1{
  border-right: 2px solid rgb(237, 240, 243);
}
</style>
