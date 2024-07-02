<template>
  <div class="staff-component-main-container">
    <div class="staff-container">
      <div class="staff-header">
        <div class="staff-photo">Photo</div>
        <div class="staff-name">Full Name</div>
        <div class="staff-position">Position/Title</div>
        <div class="staff-department">Department</div>
        <div class="staff-contact">Contact Number</div>
        <div class="staff-email">Email Address</div>
        <div class="staff-location">Work Location</div>
        <div class="staff-status">Status</div>
      </div>
      <div class="staff-row" v-for="staff in paginatedData" :key="staff.id">
        <div class="staff-photo">
          <div><img src="../../src/assets/userPhoto/images.jpeg" alt="staff photo"></div>
        </div>
        <div class="staff-name">{{ staff.name }}</div>
        <div class="staff-position">{{ staff.position }}</div>
        <div class="staff-department">{{ staff.department }}</div>
        <div class="staff-contact">{{ staff.contact }}</div>
        <div class="staff-email">{{ staff.email }}</div>
        <div class="staff-location">{{ staff.location }}</div>
        <div class="staff-status">{{ staff.status }}</div>
      </div>
    </div>
    <Pagination
      :currentPage="currentPage"
      :totalPages="totalPages"
      @page-changed="handlePageChange"
    />
  </div>
</template>

<script>
import Pagination from './Pagination.vue';

export default {
  components: {
    Pagination
  },
  data() {
    return {
      staffData: [],
      currentPage: 1,
      itemsPerPage: 7
    };
  },
  created() {
    // Fetch data from your database
    this.staffData = [
      // Sample data
      { id: 1, photo: 'path/to/photo1.jpg', name: 'John Doe', position: 'Software Engineer', department: 'IT', contact: '(123) 456-7890', email: 'john.doe@example.com', location: 'In Office', status: 'In Office' },
      { id: 2, photo: 'path/to/photo2.jpg', name: 'Jane Smith', position: 'Marketing Manager', department: 'Marketing', contact: '(987) 654-3210', email: 'jane.smith@example.com', location: 'Remote', status: 'Remote' },
      { id: 3, photo: 'path/to/photo3.jpg', name: 'Robert Brown', position: 'HR Specialist', department: 'Human Resources', contact: '(555) 123-4567', email: 'robert.brown@example.com', location: '', status: 'Absent' },
      { id: 4, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      // Add more sample data as needed
      { id: 5, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 6, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 7, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 8, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 9, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 10, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 11, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 12, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 13, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 14, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 15, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 16, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 17, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 18, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 19, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 20, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 21, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 22, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 23, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 24, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 25, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 26, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 27, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 28, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 29, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 30, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 31, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 32, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 33, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 34, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 35, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 36, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 37, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 38, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 39, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
      { id: 40, name: 'John Doe', position: 'Manager', department: 'HR', contact: '123456789', email: 'john.doe@example.com', location: 'Office A', status: 'Active', photo: 'path_to_photo' },
    ];
  },
  computed: {
    paginatedData() {
      const start = (this.currentPage - 1) * this.itemsPerPage;
      const end = start + this.itemsPerPage;
      return this.staffData.slice(start, end);
    },
    totalPages() {
      return Math.ceil(this.staffData.length / this.itemsPerPage);
    }
  },
  methods: {
    handlePageChange(page) {
      this.currentPage = page;
    }
  }
};
</script>

<style scoped>
.staff-component-main-container{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
}

.staff-container {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.staff-header, .staff-row {
  display: flex;
  width: 100%;
}

.staff-header {
  font-weight: bold;
  padding: 10px 10px 10px 10px;
  background: rgb(255, 255, 255);
  margin-bottom: 7px;
}

.staff-header > div {
  height: 22px;
  padding: 0 0 0 12px;
}

.staff-header > .staff-photo {
  border-radius: 0;
  width: 60px;
}

.staff-row {
  border-radius: 10px;
  overflow: hidden;
  margin-bottom: 7px;
  background: rgb(255, 255, 255);
  padding: 10px;
}

.staff-row .staff-photo {
  border-radius: 0;
  overflow: hidden;
}

.staff-row .staff-photo > div {
  height: 49px;
  width: 49px;
  margin: auto;
  overflow: hidden;
}

.staff-row .staff-photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 100%;
}

.staff-photo,
.staff-name,
.staff-position,
.staff-department,
.staff-contact,
.staff-email,
.staff-location,
.staff-status {
  flex-shrink: 0;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
  padding: 12px;
}

/* Set fixed widths for columns */
.staff-photo {
  width: 60px; /* Adjust as necessary */
  padding: 0;
}

.staff-name {
  width: 15%; /* Adjust as necessary */
}

.staff-position {
  width: 15%; /* Adjust as necessary */
}

.staff-department {
  width: 10%; /* Adjust as necessary */
}

.staff-contact {
  width: 13%; /* Adjust as necessary */
}

.staff-email {
  width: 20%; /* Adjust as necessary */
}

.staff-location {
  width: 13%; /* Adjust as necessary */
}

.staff-status {
  width: 8%; /* Adjust as necessary */
}
</style>
