<template>
  <q-card class="profiles-main-container full-width" flat>
    <q-tabs
      v-model="tab2"
      dense
      class="text-grey profile-tab-container"
      active-color="primary"
      indicator-color="primary"
      align="justify"
      narrow-indicator
      content-class="tabs-background"
      active-class="profile-tab-active"
    >
      <q-tab :ripple="false" class="" name="Staffs" label="Staff" />
      <q-tab :ripple="false" name="Hobbers" label="Hobbers" />
      <q-tab :ripple="false" name="Interns" label="Interns" />
      <q-tab :ripple="false" name="Corpers" label="Corpers" />
      <q-tab :ripple="false" name="Siwes" label="Siwes" />
    </q-tabs>

    <q-separator />

    <q-tab-panels class="" v-model="tab2" animated style="height: 94.7%">
      <q-tab-panel class="" name="Staffs">
        <Staffs @staff-clicked="handleStaffClick" />
      </q-tab-panel>

      <q-tab-panel name="Corpers">
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

      <q-tab-panel name="Hobbers">
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

      <q-tab-panel name="Interns">
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

      <q-tab-panel name="Siwes">
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
  </q-card>
</template>

<script>
import { ref, computed } from "vue";
import Staffs from "src/components/Staffs.vue";

export default {
  name: "profilesComponent",

  components: {
    Staffs,
  },
  data() {
    return {
    };
  },

  methods: {
    toggleProfileQv(data) {
      this.$emit('toggle-profile', data);
    },
    handleStaffClick(staff) {
      this.$emit('staff-clicked', staff);
    }
  },
  setup() {
    return {
      tab2: ref("Staffs"),
    };
  },
};
</script>

<!--  -->

<style>
.profiles-main-container {
  height: 100%;
  position: relative;
}
.q-panel-parent {
  background: none;
}
.q-panel-parent * {
  border: none;
  padding: 0;
  margin: 0;
  background: none;
}

.q-panel-parent hr {
  display: none;
}
.q-panel-parent .q-focus-helper {
  display: none;
}
.tabs-background {
  background: none;
}
.tabs-background .q-tab__content {
  background: rgb(243, 245, 248);
  width: 100%;
  margin: 0 6px 0 0;
  border-radius: 15px 15px 0 0;
}
.tabs-background .profile-tab-active > div {
  background: rgb(255, 255, 255);
  color: rgb(51, 51, 51);
}
.tabs-background .q-tab__indicator {
  display: none;
}

/*  Pagination From Pagination Component */

.pagination {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 15px;
  width: 100%;
  height: 6%;
  background-color: rgb(237, 240, 243);
}

.pagination button {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 7px;
  height: 30px;
  width: 30px;
  margin: 5px 5px;
  border: none;
  background-color: rgb(243, 245, 248);
  color: rgb(166, 166, 166);
  cursor: pointer;
  box-shadow: 0 0 20px rgb(205, 205, 205);
}

.pagination button:disabled {
  background-color: #ddd;
  cursor: not-allowed;
}

.pagination .active {
  background-color: rgb(255, 255, 255);
  color: black;
  font-weight: bolder;
}

/* Style for ellipsis */
.ellipsis {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  max-width: 0; /* Ensures that ellipsis works with overflow hidden */
  width: 20%; /* Ensure it takes up all available width */
}
</style>


