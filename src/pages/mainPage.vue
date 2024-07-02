<template>
  <div class="main-container">
    <div class="side-1">
      <div class="grey-logo">
        <q-img src="../../src/assets/GS-LOGO2.png" />
      </div>
      <div class="side-1-nav-bar-container">
        <nav class="side-1-nav-bar">
          <div class="home"><SvgIcon name="home" /></div>
          <div class="task1"><SvgIcon name="dashboard" /></div>
          <div class="profiles"><SvgIcon name="assessment" /></div>
          <div class="holder1"><SvgIcon name="work_history" /></div>
          <div class="holder2"><SvgIcon name="setting" /></div>
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
            <q-tab :ripple="false" class="" name="mails">
              <div class="menu">Profile</div>
            </q-tab>
            <q-tab :ripple="false" name="alarms">
              <div class="menu">Task</div>
            </q-tab>
            <q-tab :ripple="false" name="movies">
              <div class="menu">Activity</div>
            </q-tab>
          </q-tabs>
        </div>
      </template>

      <template v-slot:after>
        <div class="content-wrapper">
          <div class="content-title-container">
            <div class="page-title">Profile / Staff</div>
          </div>
          <q-tab-panels
            v-model="tab"
            animated
            swipeable
            vertical
            transition-prev="jump-up"
            transition-next="jump-up"
            class=""
          >
            <q-tab-panel style="width: 100%; height: 100%" name="mails">
              <div
                class="main-content-container"
                style="height: 100%; overflow: "
              >
                <profiles />
              </div>
            </q-tab-panel>

            <q-tab-panel name="alarms">
              <div
                class=""
                style="
                  width: 100%;
                  height: 100%;
                  background-color: white;
                  display: flex;
                  flex-direction: column;
                  justify-content: space-evenly;
                  align-items: center;
                "
              >
                <h3 class="text-grey-5">Work in progress</h3>

                <img
                  src="../../src/assets/tempPlaceholders/uct.png"
                  alt=""
                  style="width: 50%"
                />
              </div>
            </q-tab-panel>

            <q-tab-panel name="movies">
              <div
                class=""
                style="
                  width: 100%;
                  height: 100%;
                  background-color: white;
                  display: flex;
                  flex-direction: column;
                  justify-content: space-evenly;
                  align-items: center;
                "
              >
                <h3 class="text-grey-5">Work in progress</h3>

                <img
                  src="../../src/assets/tempPlaceholders/uct.png"
                  alt=""
                  style="width: 50%"
                />
              </div>
            </q-tab-panel>
          </q-tab-panels>
        </div>
      </template>
    </q-splitter>
  </div>
</template>

<script>
import { ref } from "vue";
import profiles from "src/components/profiles.vue";
import Staffs from "src/components/Staffs.vue";
import SvgIcon from "src/components/SvgIcon.vue";

export default {
  components: {
    profiles,
    Staffs,
    SvgIcon,
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
    background: #878787;
  }

  .side-1 {
    width: 9%;
    background: rgb(255, 255, 255);
    border-right: 3px solid rgb(237, 240, 243);
  }

  .side-1 .grey-logo {
    width: 100%;
    padding-top: ;
    display: flex;
    height: 16%;
    justify-content: center;
    align-items: center;
  }

  .side-1 .grey-logo .q-img {
    width: 50%;
    flex-shrink: 0;
  }

  .side-1 .side-1-nav-bar-container {
    height: 84%;
    display: flex;
    justify-content: center;
    padding-top: 60px;
  }

  .side-1 .side-1-nav-bar-container .side-1-nav-bar {
    width: 100%;
    height: 70%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
  }

  .q-splitter {
    overflow: hidden;
    min-width: 91%;
    max-width: 91%;
    overflow: hidden;
  }

  .q-splitter .q-splitter__separator {
    opacity: 0;
    border: 5px solid;
    display: none;
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
    font-size: 30px;
    font-weight: 500;
    letter-spacing: 5px;
    color: rgb(76, 76, 76);
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
    color: rgb(51, 51, 51);
    font-weight: 500;
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
    padding: 0 2% 0px 2%;
    height: 100%;
    background-color: rgb(237, 240, 243);
  }

  .content-wrapper .q-tab-panels:nth-child(2) {
    height: 76%;
    margin: 5% 0 0 0;
    box-sizing: border-box;
  }

  .content-title-container {
    height: 16%;
    width: 100%;
    display: flex;
    align-items: center;
    box-sizing: border-box;
  }

  .content-title-container .page-title {
    font-size: 30px;
  }
}
</style>
