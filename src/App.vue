<template>
  <div class="container">
    <div class="row mt-5">
      <div class="col-md-12">
        <AccordionItems :formDataArray="formDataArray" />
      </div>
      <div class="col-md-12">
        <div class="card">
          <div class="card-header">เขียนคำร้องขอลาออก</div>
          <div class="card-body">
            <form class="form">
              <div class="row">
                <div class="col-md-4">
                  <div class="form-group">
                    <label for="date">Date:</label>
                    <input
                      class="form-control"
                      type="date"
                      v-model="formData.date"
                      id="date"
                    />
                  </div>
                </div>
                <div class="col-md-8">
                  <div class="form-group">
                    <label for="subject">Subject:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.subject"
                      id="subject"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="to">To:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.to"
                      id="to"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="name">Name:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.name"
                      id="name"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="name">Surname :</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.name"
                      id="name"
                    />
                  </div>
                </div>
                <div class="col-md-12">
                  <div class="form-group">
                    <label for="studentID">Student ID:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.studentID"
                      id="studentID"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="major">Major:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.major"
                      id="major"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="faculty">Faculty:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.faculty"
                      id="faculty"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="telephone">Telephone:</label>
                    <input
                      class="form-control"
                      type="text"
                      v-model="formData.telephone"
                      id="telephone"
                      maxlength="10"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="email">Email:</label>
                    <input
                      class="form-control"
                      type="email"
                      v-model="formData.email"
                      id="email"
                    />
                  </div>
                </div>

                <div class="col-md-12">
                  <div class="form-group">
                    <label for="reason">Reason:</label>
                    <textarea
                      class="form-control"
                      v-model="formData.reason"
                      id="reason"
                    ></textarea>
                  </div>
                </div>
                <div class="col-md-12 text-center">
                  <button
                    type="submit"
                    class="btn btn-primary"
                    @click.prevent="submitForm"
                  >
                    Submit
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AccordionItems from "./components/AccordionItems.vue";
export default {
  data() {
    return {
      formData: {
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
      },
      formDataArray: [],
    };
  },
  components: {
    AccordionItems,
  },
  methods: {
    submitForm() {
      // Add the form data to the formDataArray
      this.formDataArray.push(this.formData);

      // Reset the formData object
      this.formData = {
        date: null,
        subject: "",
        to: "",
        name: "",
        studentID: "",
        major: "",
        faculty: "",
        telephone: "",
        email: "",
        reason: "",
      };
    },
  },
};
</script>
