<template>
  <div class="main-container">
    <div class="side-1">
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
    <q-splitter v-model="splitterModel" style="max-height: 100%" class="">
      <template v-slot:before>
        <div class="side-2">
          <div class="app-title">GMS</div>
          <q-tabs
            v-model="tab"
            vertical
            class="text-teal tab-menu"
            active-class="active-menu"
            active-color="black"
            no-caps
          >
            <q-tab :ripple="false" class="" name="mails"
              ><div class="menu">Profile</div></q-tab
            >
            <q-tab :ripple="false" name="alarms"
              ><div class="menu">Profile</div></q-tab
            >
            <q-tab :ripple="false" name="movies"
              ><div class="menu">Profile</div></q-tab
            >
          </q-tabs>
        </div>
      </template>

      <template v-slot:after>
        <div class="content-wrapper">
          <div class="content-title-container">
            <div class="text-h4 q-mb-md">Alarms</div>
          </div>
          <q-tab-panels
            v-model="tab"
            animated
            swipeable
            vertical
            transition-prev="jump-up"
            transition-next="jump-up"
          >
            <q-tab-panel name="mails">
              <div class="main-content-container">
                <profiles />
              </div>
            </q-tab-panel>

            <q-tab-panel name="alarms">
              <p>
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
                praesentium cumque magnam odio iure quidem, quod illum numquam
                possimus obcaecati commodi minima assumenda consectetur culpa
                fuga nulla ullam. In, libero.
              </p>
              <p>
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
                praesentium cumque magnam odio iure quidem, quod illum numquam
                possimus obcaecati commodi minima assumenda consectetur culpa
                fuga nulla ullam. In, libero.
              </p>
            </q-tab-panel>

            <q-tab-panel name="movies">
              <div class="text-h4 q-mb-md">Movies</div>
              <p>
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
                praesentium cumque magnam odio iure quidem, quod illum numquam
                possimus obcaecati commodi minima assumenda consectetur culpa
                fuga nulla ullam. In, libero.
              </p>
              <p>
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
                praesentium cumque magnam odio iure quidem, quod illum numquam
                possimus obcaecati commodi minima assumenda consectetur culpa
                fuga nulla ullam. In, libero.
              </p>
              <p>
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quis
                praesentium cumque magnam odio iure quidem, quod illum numquam
                possimus obcaecati commodi minima assumenda consectetur culpa
                fuga nulla ullam. In, libero.
              </p>
            </q-tab-panel>
          </q-tab-panels>
        </div>
      </template>
    </q-splitter>
  </div>
</template>

<script>
import { ref } from "vue";
import profiles from 'src/components/profiles.vue'

export default {
  components: {
    profiles
  },
  setup() {
    return {
      tab: ref("mails"),
      splitterModel: ref(20),
    };
  },
};
</script>



<!--  -->

<style>
/* Break-points */

@media only screen and (min-width: 600px) {
  body,
  html {
    width: 100%;
    height: 100%;
  }
  .main-container {
    display: flex;
    height: 100vh;
    width: 100%;
    overflow: hidden;
    background-color: rgb(237, 240, 243);
  }
  .side-1 {
    width: 9%;
    background: rgb(255, 255, 255);
    border-right: 3px solid rgb(237, 240, 243);
  }
  .q-splitter {
    overflow: hidden;
    min-width: 91%;
    max-width: 91%;
    overflow: hidden;
  }
  .q-splitter .q-splitter__separator {
    opacity: 0;
  }
  .q-splitter__before {
    min-width: 19%;
    max-width: 19%;
  }
  .side-2 {
    height: 100%;
  }
  .side-2 .app-title {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 16%;
    border-bottom: 2px solid rgb(237, 240, 243);
  }
  .side-2 .q-tabs__content {
    min-height: 20%;
    max-height: 84%;
    padding: 100px 0px 0 0px;
  }
  .q-hoverable > div {
    background: rgb(255, 255, 255);
  }
  .q-hoverable .q-tab__indicator {
    background: #c1c8cd;
    width: 4px;
    border-radius: 10px 0 0 10px;
  }
  .side-2 .q-tabs__content * {
    display: block;
    text-align: left;
    padding: 0px;
    margin: 0px;
  }
  .active-menu > div > div {
    background-color: #f2f5f7;
  }
  .side-2 .q-tabs__content .menu {
    padding: 16px 10px 16px 10%;
    border-radius: 15px;
    font-size: 1.5em;
    margin: 20px auto;
    width: 88%;
  }
  .tab-menu > div {
    color: rgb(152, 162, 179);
  }
  .q-splitter__before {
    min-height: 90%;
    max-height: 100%;
    overflow: hidden;
    background-color: #ffffff;
  }
  .q-splitter__after {
    min-width: 79%;
    max-width: 79%;
  }
  .q-splitter__after .q-panel-parent {
    min-width: 100%;
    max-width: 100%;
  }

  /* Content Component */
  .content-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    height: 100%;
    background-color: rgb(237, 240, 243);
  }
  .content-title-container{
    background: red;
    height: 30%;
  }
  .q-panel-parent{
    background: red;
    height: 100%;
  }
}
</style>
