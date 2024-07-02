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
        <Staffs />
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
      staffData: [
        {
          id: 1,
          photo: "https://via.placeholder.com/50",
          name: "John Doe",
          position: "Software Engineer",
          department: "IT",
          contact: "(123) 456-7890",
          email: "john.doe@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 2,
          photo: "https://via.placeholder.com/50",
          name: "Jane Smith",
          position: "Marketing Manager",
          department: "Marketing",
          contact: "(987) 654-3210",
          email: "jane.smith@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 3,
          photo: "https://via.placeholder.com/50",
          name: "Robert Brown",
          position: "HR Specialist",
          department: "Human Resources",
          contact: "(555) 123-4567",
          email: "robert.brown@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 4,
          photo: "https://via.placeholder.com/50",
          name: "Emily Johnson",
          position: "Financial Analyst",
          department: "Finance",
          contact: "(222) 333-4444",
          email: "emily.johnson@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 5,
          photo: "https://via.placeholder.com/50",
          name: "Michael Clark",
          position: "Sales Manager",
          department: "Sales",
          contact: "(777) 888-9999",
          email: "michael.clark@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 6,
          photo: "https://via.placeholder.com/50",
          name: "Sarah Lee",
          position: "Product Manager",
          department: "Product",
          contact: "(111) 222-3333",
          email: "sarah.lee@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 7,
          photo: "https://via.placeholder.com/50",
          name: "Daniel Wilson",
          position: "Operations Coordinator",
          department: "Operations",
          contact: "(444) 555-6666",
          email: "daniel.wilson@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 8,
          photo: "https://via.placeholder.com/50",
          name: "Jessica Brown",
          position: "HR Manager",
          department: "Human Resources",
          contact: "(888) 999-0000",
          email: "jessica.brown@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 9,
          photo: "https://via.placeholder.com/50",
          name: "David White",
          position: "Software Developer",
          department: "IT",
          contact: "(666) 777-8888",
          email: "david.white@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 10,
          photo: "https://via.placeholder.com/50",
          name: "Jennifer Davis",
          position: "Marketing Specialist",
          department: "Marketing",
          contact: "(333) 444-5555",
          email: "jennifer.davis@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 11,
          photo: "https://via.placeholder.com/50",
          name: "Andrew Miller",
          position: "Financial Planner",
          department: "Finance",
          contact: "(123) 456-7890",
          email: "andrew.miller@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 12,
          photo: "https://via.placeholder.com/50",
          name: "Emma Wilson",
          position: "Sales Executive",
          department: "Sales",
          contact: "(987) 654-3210",
          email: "emma.wilson@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 13,
          photo: "https://via.placeholder.com/50",
          name: "Kevin Harris",
          position: "Product Designer",
          department: "Product",
          contact: "(555) 123-4567",
          email: "kevin.harris@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 14,
          photo: "https://via.placeholder.com/50",
          name: "Olivia Garcia",
          position: "Operations Manager",
          department: "Operations",
          contact: "(222) 333-4444",
          email: "olivia.garcia@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 15,
          photo: "https://via.placeholder.com/50",
          name: "Ryan Martinez",
          position: "HR Assistant",
          department: "Human Resources",
          contact: "(777) 888-9999",
          email: "ryan.martinez@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 16,
          photo: "https://via.placeholder.com/50",
          name: "Sophia Lopez",
          position: "Software Engineer",
          department: "IT",
          contact: "(111) 222-3333",
          email: "sophia.lopez@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 17,
          photo: "https://via.placeholder.com/50",
          name: "Noah Young",
          position: "Marketing Director",
          department: "Marketing",
          contact: "(444) 555-6666",
          email: "noah.young@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 18,
          photo: "https://via.placeholder.com/50",
          name: "Mia King",
          position: "Financial Analyst",
          department: "Finance",
          contact: "(888) 999-0000",
          email: "mia.king@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 19,
          photo: "https://via.placeholder.com/50",
          name: "Ethan Brown",
          position: "Sales Representative",
          department: "Sales",
          contact: "(666) 777-8888",
          email: "ethan.brown@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 20,
          photo: "https://via.placeholder.com/50",
          name: "Ava Taylor",
          position: "Product Manager",
          department: "Product",
          contact: "(333) 444-5555",
          email: "ava.taylor@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 21,
          photo: "https://via.placeholder.com/50",
          name: "Alexander Green",
          position: "Operations Coordinator",
          department: "Operations",
          contact: "(123) 456-7890",
          email: "alexander.green@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 22,
          photo: "https://via.placeholder.com/50",
          name: "Charlotte Hall",
          position: "HR Manager",
          department: "Human Resources",
          contact: "(987) 654-3210",
          email: "charlotte.hall@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 23,
          photo: "https://via.placeholder.com/50",
          name: "James White",
          position: "Software Developer",
          department: "IT",
          contact: "(555) 123-4567",
          email: "james.white@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 24,
          photo: "https://via.placeholder.com/50",
          name: "Grace Lee",
          position: "Marketing Specialist",
          department: "Marketing",
          contact: "(222) 333-4444",
          email: "grace.lee@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 25,
          photo: "https://via.placeholder.com/50",
          name: "Benjamin Scott",
          position: "Financial Planner",
          department: "Finance",
          contact: "(777) 888-9999",
          email: "benjamin.scott@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 26,
          photo: "https://via.placeholder.com/50",
          name: "Lily Johnson",
          position: "Sales Executive",
          department: "Sales",
          contact: "(111) 222-3333",
          email: "lily.johnson@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 27,
          photo: "https://via.placeholder.com/50",
          name: "Christopher Martinez",
          position: "Product Designer",
          department: "Product",
          contact: "(444) 555-6666",
          email: "christopher.martinez@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 28,
          photo: "https://via.placeholder.com/50",
          name: "Samantha Wilson",
          position: "Operations Manager",
          department: "Operations",
          contact: "(888) 999-0000",
          email: "samantha.wilson@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 29,
          photo: "https://via.placeholder.com/50",
          name: "Daniel Brown",
          position: "HR Assistant",
          department: "Human Resources",
          contact: "(666) 777-8888",
          email: "daniel.brown@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 30,
          photo: "https://via.placeholder.com/50",
          name: "Sophie Rodriguez",
          position: "Software Engineer",
          department: "IT",
          contact: "(333) 444-5555",
          email: "sophie.rodriguez@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 31,
          photo: "https://via.placeholder.com/50",
          name: "Matthew Young",
          position: "Marketing Director",
          department: "Marketing",
          contact: "(123) 456-7890",
          email: "matthew.young@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 32,
          photo: "https://via.placeholder.com/50",
          name: "Madison King",
          position: "Financial Analyst",
          department: "Finance",
          contact: "(987) 654-3210",
          email: "madison.king@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 33,
          photo: "https://via.placeholder.com/50",
          name: "David Wilson",
          position: "Sales Representative",
          department: "Sales",
          contact: "(555) 123-4567",
          email: "david.wilson@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 34,
          photo: "https://via.placeholder.com/50",
          name: "Isabella Taylor",
          position: "Product Manager",
          department: "Product",
          contact: "(222) 333-4444",
          email: "isabella.taylor@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 35,
          photo: "https://via.placeholder.com/50",
          name: "Andrew Green",
          position: "Operations Coordinator",
          department: "Operations",
          contact: "(777) 888-9999",
          email: "andrew.green@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 36,
          photo: "https://via.placeholder.com/50",
          name: "Avery Hall",
          position: "HR Manager",
          department: "Human Resources",
          contact: "(111) 222-3333",
          email: "avery.hall@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 37,
          photo: "https://via.placeholder.com/50",
          name: "Elijah White",
          position: "Software Developer",
          department: "IT",
          contact: "(444) 555-6666",
          email: "elijah.white@example.com",
          location: "In Office",
          status: "In Office",
        },
        {
          id: 38,
          photo: "https://via.placeholder.com/50",
          name: "Scarlett Lee",
          position: "Marketing Specialist",
          department: "Marketing",
          contact: "(888) 999-0000",
          email: "scarlett.lee@example.com",
          location: "Remote",
          status: "Remote",
        },
        {
          id: 39,
          photo: "https://via.placeholder.com/50",
          name: "Gabriel Martinez",
          position: "Financial Planner",
          department: "Finance",
          contact: "(666) 777-8888",
          email: "gabriel.martinez@example.com",
          location: "",
          status: "Absent",
        },
        {
          id: 40,
          photo: "https://via.placeholder.com/50",
          name: "Hannah Garcia",
          position: "Sales Executive",
          department: "Sales",
          contact: "(333) 444-5555",
          email: "hannah.garcia@example.com",
          location: "In Office",
          status: "In Office",
        },
      ],
      currentPage: 1,
      pageSize: 10,
    };
  },
  computed: {
    totalPages() {
      return Math.ceil(this.staffData.length / this.pageSize);
    },
    paginatedData() {
      const start = (this.currentPage - 1) * this.pageSize;
      const end = start + this.pageSize;
      return this.staffData.slice(start, end);
    },
  },
  methods: {
    goToPage(page) {
      this.currentPage = page;
    },
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


