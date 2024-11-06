<script setup>
const user = {
  image:
    'https://scontent.fdad3-1.fna.fbcdn.net/v/t39.30808-6/332876245_1318915528957404_7730218585985673496_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=6ee11a&_nc_eui2=AeHDfrcEkAMgcoKDclOoPFBl0AVOaphSthLQBU5qmFK2EuZBCYj_bdVcaJPpVtgHIC6BMdXm120pElBJto6HqoNs&_nc_ohc=ETdAgqGUOVUQ7kNvgFkTqmi&_nc_zt=23&_nc_ht=scontent.fdad3-1.fna&_nc_gid=AWOLD32ij3-hO_9Kpnb9dI_&oh=00_AYDcRjf6xlc8sZa-VaS6AahneXjsZHdnkL8OlhJxG_Sq1A&oe=672E21FE',
  name: 'Lê Nguyên Hùng',
  job: 'Font-end Developer',
  introduce:
    'A Front-End Developer builds and designs the user interface of websites and applications using HTML, CSS, and JavaScript. They focus on creating interactive, visually appealing experiences that work seamlessly across devices and browsers.',
}

const editUser = () => {
  alert('Updated')
}
</script>

<template>
  <div class="extra-exercises">
    <h1>Personal Information</h1>
    <div class="cart">
      <img :src="user.image" alt="avatar" />
      <div class="text-info">
        <p class="name">{{ user.name }}</p>
        <p class="job">{{ user.job }}</p>
        <p class="introduce">{{ user.introduce }}</p>
        <div class="button">
          <button @click="editUser">Edit</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cart {
  border: 1px solid rgb(222, 222, 222);
  box-shadow: 5px 10px 10px #dadada;
  border-radius: 12px;
  width: 500px;
  overflow: hidden;
}

.cart img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  object-position: top;
}
.text-info {
  padding: 15px 30px;
}
.name {
  font-size: 25px;
  font-weight: 500;
  margin-bottom: 10px;
}
.job {
  font-size: 19px;
  opacity: 0.7;
  margin-bottom: 30px;
}
.introduce {
  font-size: 16px;
  color: #333;
  letter-spacing: 1px;
  line-height: 23px;
  margin-bottom: 50px;
}
.button {
  display: flex;
  justify-content: flex-end;
  margin: 10px 0;
}
button {
  padding: 14px 35px;
  border-radius: 30px;
  border: none;
  font-weight: 600;
  color: white;
  cursor: pointer;
  background-color: #504472;
  transition: 0.2s ease-in-out;
}
button:hover {
  background-color: #8774ba;
}
</style>
