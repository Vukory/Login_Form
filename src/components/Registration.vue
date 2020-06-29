<template>
  <div id="registration-form">
    <form>
      <div class="input-field">
        <label for="first-name-field">First Name</label>
        <input
          id="first-name-field"
          type="text"
          aria-label="First Name"
          required
          name="first-name"
          placeholder="Firstname"
          v-model="firstName"
        />
      </div>
      <div class="input-field">
        <label for="last-name-field">Last Name</label>
        <input
          id="last-name-field"
          type="text"
          aria-label="Last Name"
          required
          name="last-name"
          placeholder="Lastname"
          v-model="lastName"
        />
      </div>
      <div class="input-field">
        <label for="email-field">Email</label>
        <input
          id="email-field"
          type="email"
          aria-label="Email"
          required
          pattern=".+?@.+?\..+"
          name="email"
          placeholder="vuki@el.art"
          v-model="email"
        />
      </div>
      <div class="input-field">
        <label for="password-field">Password</label>
        <input
          id="password-field"
          type="password"
          aria-label="Password"
          minlength="8"
          required
          name="password"
          v-model="password"
        />
      </div>
      <div class="input-field">
        <label for="verify-password-field">Verify Password</label>
        <input
          id="verify-password-field"
          type="password"
          aria-label="Verify Password"
          minlength="8"
          required
          name="verify-password"
          v-model="verifyPassword"
        />
      </div>
      <div v-if="!passwordsMatch()" id="errors">The passwords do not match.</div>
      <button>Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      firstName: null,
      lastName: null,
      email: null,
      password: null,
      verifyPassword: null
    };
  },
  methods: {
    passwordsMatch() {
      return this.password === this.verifyPassword;
    }
  }
};
</script>

<style scoped>
#registration-form,
form,
.input-field {
  display: flex;
  justify-content: center;
  flex-direction: column;
}

#registration-form {
  background-color: #a2bbac73;
  border-radius: 1em;
  align-items: center;
  padding: 1em;
}

form {
  width: 50%;
  height: 90%;

  align-items: center;
}

.input-field {
  width: 100%;
  margin: 0 0 1em 0;
}

.input-field label {
  float: left;
  margin: 0 0 0.5em 0;
}

input {
  width: 100%;
  border-radius: 10px;
  padding: 0.3em 0.5em;
  height: 2em;
  border: none;
}

button {
  border: none;
  border-radius: 1em;
  width: 8em;
  height: 3em;
  background-color: #3d5044;
  color: #e2e0c1;
}

button:hover {
  background-color: #64806e;
  cursor: pointer;
}

#errors {
  color: #862b2b;
  margin: 0 0 1em 0;
}
</style>