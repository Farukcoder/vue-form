<template>
  <div>
    <form>
      <div class="row">
        <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
          <h1>Form Handling</h1>
          <hr>
          <div class="mb-3">
            <label for="email" class="form-label">Mail</label>
            <input type="email" id="email" class="form-control" v-model="userData.email">
          </div>
          <div class="mb-3">
            <label for="password" class="form-label">Password</label>
            <input type="password" id="password" class="form-control" v-model.lazy="userData.password">
          </div>
          <div class="mb-3">
            <label for="age" class="form-label">Age</label>
            <input type="number" id="age" class="form-control" v-model="userData.age">
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
          <div class="mb-3">
            <label for="message" class="form-label">Message</label>
            <textarea id="message" rows="5" class="form-control" v-model="message"></textarea>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
          <div class="mb-3">
            <div class="form-check">
              <input class="form-check-input" type="checkbox" id="sendmail" value="SendMail" v-model="sendMail">
              <label class="form-check-label" for="sendmail">Send Mail</label>
            </div>
            <div class="form-check">
              <input class="form-check-input" type="checkbox" id="sendInfomail" value="SendInfoMail" v-model="sendMail">
              <label class="form-check-label" for="sendInfomail">Send Informal</label>
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
          <div class="mb-3">
            <div class="form-check">
              <input class="form-check-input" type="radio" name="gender" id="male" value="Male" v-model="gender">
              <label class="form-check-label" for="male">Male</label>
            </div>
            <div class="form-check">
              <input class="form-check-input" type="radio" name="gender" id="female" value="Female" v-model="gender">
              <label class="form-check-label" for="female">Female</label>
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
          <div class="mb-3">
            <label for="priority" class="form-label">Priority</label>
            <select id="priority" class="form-select" v-model="selectPrioritey">
              <option v-for="priority in priorities" :key="priority">{{priority}}</option>
            </select>
          </div>
        </div>
      </div>
      <hr>
      <div class="row">
        <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
          <button type="submit" class="btn btn-primary" @click.prevent="submited">Submit!</button>
        </div>
      </div>
    </form>
    <hr>
    <div class="row" v-if="isSubmited">
      <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
        <div class="card">
          <div class="card-header">
            <h4>Your Data</h4>
          </div>
          <div class="card-body">
            <p>Mail:{{userData.email}}</p>
            <p>Password:{{userData.password}}</p>
            <p>Age:{{userData.age}}</p>
            <p style="white-space: pre-line">Message:{{message}}</p>
            <p><strong>Send Mail?</strong></p>
            <ul>
              <li v-for="mail in sendMail" :key="mail">
                {{mail}}
              </li>
            </ul>
            <p>Gender: {{ gender }}</p>
            <p>Priority: {{selectPrioritey}}</p>
            <p>Switched:</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userData: {
        email: '',
        password: '',
        age: 0,
      },
      message: '',
      sendMail: [],
      gender: 'Male',
      selectPrioritey: 'Medium',
      priorities: ['High', 'Medium', 'Low'],
      isSubmited: false
    }
  },
  methods:{
    submited(){
      this.isSubmited = true;
    }
  },
  destroyed() {
    console.log('Destroy');
  },
  activated() {
    console.log('Activated');
  },
  deactivated() {
    console.log('Deactivated');
  }
}
</script>

<style>
/* Add any custom styling here if needed */
</style>
