<template>
  <div class="page">
    <h4>Thêm thông tin nhân viên</h4>
    <ContactForm :contact="contact" @submit:contact="postContact" />
    <p>{{ message }}</p>
  </div>
</template>
<script>
import ContactForm from "../components/ContactForm.vue";
import ContactService from "../services/contact.service";
export default {
  components: {
    ContactForm,
  },
  data() {
    return {
      contact: {},
      message: "",
    };
  },
  methods: {
    async postContact(data) {
      try {
        await ContactService.create(data);
        alert("Thông tin được thêm thành công.");
        this.$router.push({ name: "contactbook" });
      } catch (error) {
        console.log(error);
      }
    },
  },
  created() {
    this.postContact();
    this.message = "";
  },
};
</script>
