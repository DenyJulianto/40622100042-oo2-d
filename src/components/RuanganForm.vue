<template>
    <v-container>
      <div class="outer-box">
        <h2>Entry Data Ruangan</h2>
        <v-row>
          <v-text-field label="Kode" v-model="ruangan.kode" variant="outlined"></v-text-field>
        </v-row>
        <v-row>
          <v-text-field label="Nama Ruangan" v-model="ruangan.nama" variant="outlined"></v-text-field>
        </v-row>
        <v-row>
          <v-btn color="blue" @click="submitRuangan">Submit</v-btn>
        </v-row>
      </div>
    </v-container>
  </template>
  
  <script lang="ts">
  import { Ruangan } from '@/model/Ruangan'
  
  export default {
    data() {
      return {
        ruangan: new Ruangan('', '')
      }
    },
    methods: {
      submitRuangan() {
        if (!this.ruangan.kode || !this.ruangan.nama) {
          alert('Field Kode dan Nama Ruangan belum terisi')
        } else {
          alert('Data Ruangan ' + this.ruangan.nama + ' berhasil disimpan')
          this.ruangan = new Ruangan('', '')
        }
      }
    }
  }
  </script>
  
  <style scoped>
  h2 {
    padding-bottom: 30px;
  }
  
  .outer-box {
    border: 2px solid #ccc;
    padding: 90px;
  }
  </style>