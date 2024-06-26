<template>
   <q-card class="full-width" flat>
        <q-tabs
          v-model="tab2"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
        >
          <q-tab name="Staffs" label="Staffs" />
          <q-tab name="alarmsu" label="Alarmsu" />
          <q-tab name="movies4" label="Movies4" />
        </q-tabs>

        <q-separator />

        <q-tab-panels v-model="tab2" animated>
          <q-tab-panel name="Staffs">
            <div class="text-h6">Staffs</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>

          <q-tab-panel name="alarmsu">
            <div class="text-h6">Alarmsu</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>

          <q-tab-panel name="movies4">
            <div class="text-h6">Movies4</div>
            Lorem ipsum dolor sit amet consectetur adipisicing elit.
          </q-tab-panel>
        </q-tab-panels>
      </q-card>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'profilesComponent',
  setup () {
    return {
      tab2: ref('Staffs')
    }
  }
}
</script>
