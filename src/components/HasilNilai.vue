<template>
  <div>
    <nav>
      <div class="nav__content">
        <div class="logo"><i><a href="#">INSEMTIF</a></i></div>
        <label for="check" class="checkbox">
          <i class="ri-menu-line"></i>
        </label>
        <input type="checkbox" name="check" id="check" />
        <ul>
          <li><a href="Dashbord.html">Dashbord</a></li>
          <li><a href="">Input NIlai KP/TA</a></li>
          <li><a href="akun.html">Akun</a></li>
          <li><a href="Logout.html">Keluar</a></li>
        </ul>
      </div>
    </nav>
    <div class="container">
      <h2>Daftar Mahasiswa Tugas Akhir</h2>
      <div class="search-bar">
        <input type="text" id="search-input" placeholder="Cari Nama" v-model="searchTerm" />
      </div>
      <div class="table-container">
        <table>
          <thead>
            <tr>
              <th class="text-center">Nama</th>
              <th class="text-center">Nim</th>
              <th class="text-center">Status</th>
            </tr>
          </thead>
          <tbody id="table-body">
            <tr v-for="(mahasiswa, index) in filteredMahasiswas" :key="index">
              <td>{{ mahasiswa.nama }}</td>
              <td>{{ mahasiswa.nim }}</td>
              <td>
                <select class="status-select">
                  <option value="selesai">Selesai</option>
                  <option value="belum">Belum</option>
                </select>
                <button class="btn btn-kelola">Kelola</button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mahasiswas: [
        { nama: "Ahmad Kurniawan", nim: "12250111514" },
        { nama: "Muhammad Faruq", nim: "12250111515" },
        { nama: "Muhammad Aditya R.", nim: "12250111516" },
        { nama: "Hafidz Alhadid R.", nim: "12250111517" },
        { nama: "Aufa Hajati", nim: "12250111518" }
      ],
      searchTerm: ""
    };
  },
  computed: {
    filteredMahasiswas() {
      return this.mahasiswas.filter(mahasiswa =>
        mahasiswa.nama.toLowerCase().includes(this.searchTerm.toLowerCase())
      );
    }
  }
};
</script>

<style scoped>
:root {
  --primary-color: #f9fafc;
  --primary-color-dark: #fdfdff;
  --secondary-color: #fafafd;
  --text-dark: #ffffff;
  --extra-light: #edf0f3;
  --max-width: 1200px;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  list-style: none;
  font-family: 'Open Sans', sans-serif;
}

a {
  text-decoration: none;
}

nav {
width: 100%;
position: fixed;
top: 0;
left: 0;
background-color: #1d1f8d;
z-index: 99;
}

.nav__content {
max-width: var(--max-width);
margin: auto;
padding: 1.5rem 1rem;
display: flex;
align-items: center;
justify-content: space-between;
}

nav .logo a {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--primary-color);
  transition: 0.3s;
}
nav .logo a:hover {
  color: var(--primary-color-dark);
}

nav .checkbox {
  display: none;
}

nav input {
  display: none;
}
nav .checkbox i {
  font-size: 2rem;
  color: var(--primary-color);
  cursor: pointer;
}

ul {
  display: flex;
  align-items: center;
  gap: 1rem;
  list-style: none;
  transition: left 0.3s;
}

ul li a {
  padding: 0.5rem 1rem;
  border: 2px solid transparent;
  text-decoration: none;
  font-weight: 600;
  color: var(--text-dark);
  transition: 0.5s;
}

ul li a:hover {
  border-top-color: var(--secondary-color);
  border-bottom-color: var(--secondary-color);
  color: var(--secondary-color);
}

.wrapper .sidebar{
  background: #363636;
  position: fixed;
  top: 0;
  left: 0;
  width: 250px;
  height: 100%;
  padding: 100px 0;
}

.wrapper .sidebar .profile{
  margin-bottom: 30px;
  text-align: center;
}

.wrapper .sidebar .profile img{
  display: block;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin: auto;
}

.wrapper .sidebar .profile h3{
  color: #fdfcfc;
  margin: 30px 0 5px;
}

.wrapper .sidebar .profile p{
  color: rgb(250, 248, 248);
  font-size: 14px;
  margin: 10px;
}




body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 150px;
  text-align: center;
  margin-left: 300px;
}

.Bagian3 {
  width: 100%;
  max-width: 700px;
  margin: auto;
}

h2 {
  margin-bottom: 80px;
  font-size: 1.6rem;
}

.box-container {
  display: flex;
  justify-content: space-between;
  gap: 20px;
}

.box {
  background-color: #f0f0f0;
  padding: 40px;
  border-radius: 5px;
  text-align: center;
  width: 45%;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.box p {
  margin-bottom: 30px;
  font-size: 1.2rem;
}

.btn-lihat {
  background-color: #3498db;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
}

.btn-lihat:hover {
  background-color: #2980b9;
}

</style>
