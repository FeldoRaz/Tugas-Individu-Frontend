<script>


export default{
  data(){
    return{
      datasensor :"Belum ada"
    }
  },

  created(){
    this.sambutan()
  },
  
  methods:{
    sambutan(){
      alert("selamat datang");
    },
    async updata(){
      const data = await fetch("http://127.0.0.1:82/getdata")
      const datanya1 = await data.json()
      this.datasensor = datanya1.postData
    }
  }
}
//tempat ngoding javascript
</script>

<template>
<!----tempat ngoding html-->
  <div>
    Laporan keuangan {{ datasensor }}
    <button @click="updata" class="bg-yellow-500 p-2 rounded-2xl">Dapatkan Data</button>&NonBreakingSpace;
    <!--&NonBreakingSpace /nbsp untuk memberi space-->
    <!--Click Atl pada keybord untuk mengubah 2 atau lebih baris secara bersamaan-->
    <!--lalu untuk mengganti sebuah nama file yang sama dan secara
    bersamaan walaupun beda lokasi FILE maka diperlukan REPLACE IN FILE pada pilihan
    edit pada pjok kiri atas || setelah copas data itu lalu tinggal replace-->
    <button @click="updata" class="bg-yellow-500 p-2 rounded-2xl">Dapatkan Data2</button>
  </div>
  
</template>