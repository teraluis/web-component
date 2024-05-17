<template>
  <div class="user-profile">
    <div class="avatar">
      <span class="initials">{{ initials }}</span>
    </div>
    <div class="user-info">
      <div class="username" >{{ username }}</div>
      <div class="logout">
        <button @click="logout">{{ logtext }}</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  methods: {
    logout() {
      console.log('User logged out');
      // implementation du logout via un event emmiter ou autre equivalent en vueJS
    }
  },
  props: {
    username: {
      type: String,
      default: 'Name Lastname'
    }
  },
  data() {
    return {
      logtext: "Log out",
    };
  },
  computed: {
  initials() {
    const words = this.username.split(' ');
    return words[0].charAt(0) + words[1].charAt(0);
  }
 }
};
</script>

<style scoped>
.user-profile {
  display: flex;
  align-items: center;
  background-color: #f4f5f7; /* Couleur de fond */
  padding: 10px;
  border-radius: 8px;
  width: 200px; /* Ajuster la largeur selon les besoins */
}

.avatar {
  background-color: #004d40; /* Couleur de fond du cercle des initiales */
  color: #fff;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  font-weight: bold;
}

.user-info {
  margin-left: 10px;
}

.username {
  font-size: 14px;
  font-weight: bold;
}

.logout button {
  background: none;
  border: none;
  color: #5e6c84;
  cursor: pointer;
  padding: 0;
  margin-top: 5px;
  font-size: 12px;
}

.logout button:hover {
  text-decoration: underline;
}
</style>
