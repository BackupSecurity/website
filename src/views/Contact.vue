<template>
  <div class="about">
    <h1 class="text-primary text-bold">Contact Us</h1>
    <b-container fluid>
      <b-row>
        <b-col cols="12" md="6">
          <b-jumbotron></b-jumbotron>
        </b-col>
        <b-col cols="12" md="6">
          <b-card
            header="Contact Form"
            header-text-variant="light"
            header-tag="h4"
            header-bg-variant="primary"
          >
            <b-form>
              <b-form-group
                id="name-fieldset"
                label="Name"
                label-for="name-input"
                :invalid-feedback="invalidFeedback"
                :valid-feedback="validFeedback"
                :state="state.name"
              >
                <b-form-input
                  id="name-input"
                  v-model="form.name"
                  :state="state.name"
                  trim
                ></b-form-input>
              </b-form-group>
              <b-form-group
                id="phone-fieldset"
                label="Phone"
                label-for="phone-input"
                :invalid-feedback="invalidFeedback"
                :valid-feedback="validFeedback"
                :state="state.phone"
              >
                <b-form-input
                  id="phone-input"
                  v-model="form.phone"
                  :state="state.phone"
                  trim
                ></b-form-input>
              </b-form-group>
              <b-form-group
                id="email-fieldset"
                label="Email"
                label-for="email-input"
                :invalid-feedback="invalidFeedback"
                :valid-feedback="validFeedback"
                :state="state.email"
              >
                <b-form-input
                  id="email-input"
                  v-model="form.email"
                  :state="state.email"
                  trim
                ></b-form-input>
              </b-form-group>
              <b-form-group
                id="message-fieldset"
                label="Message"
                label-for="message-input"
                :invalid-feedback="invalidFeedback"
                :valid-feedback="validFeedback"
                :state="state.message"
              >
                <b-textarea
                  id="message-input"
                  :state="state.message"
                  v-model="form.message"
                  trim
                />
              </b-form-group>
            </b-form>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      form: {
        name: null,
        email: null,
        phone: null,
        message: null
      },
      state: {
        name: true,
        email: true,
        phone: true,
        message: true
      },
      validFeedback: "Thanks",
      invalidFeedback: "Wrong"
    };
  }
};
</script>
