<template>
    <q-page padding>
     <q-card flat>
         <q-card-section class="q-gutter-md">
             <div class="text-h5">Input Jadwal</div>
             <q-form
                  @submit="onSubmit"
                  @reset="onReset"
                  class="q-nt-lq"
                  >
                  <div class="q-gutter-md">
                  <q-input label="waktu" v-model="waktu" filled :rules="[ val => val && val.length > 0 || 'Tolong Isi Waktu']"></q-input>
                  <q-input label="judul kegiatan" v-model="judul" filled :rules="[ val => val && val.length > 0 || 'Tolong Isi Judul']"></q-input>
                  <q-input label="keterangan" v-model="keterangan" filled :rules="[ val => val && val.length > 0 || 'Tolong Isi Keterangan']"></q-input>
                  <q-btn type="submit" label="Input" color="green" unelevated></q-btn>
                  <q-btn type="reset" label="Reset" color="green" flat unelevated></q-btn>
                  </div>
             </q-form>
         </q-card-section>
     </q-card>
    </q-page>
</template>
<script>
export default {
    data () {
      return {
         waktu: null,
         judul: null,
         keterangan: null
    }
    },
    methods: {
        onReset () {
        this.waktu = null
        this.judul = null
        this.keterangan = null
        },
        onSubmit () {
         this.$q.notify({
          type: 'positive',
          message: 'Berhasil Input Jadwal'
        })
        this.$router.push({ name: 'dashboard' })
        }
    }
    }
</script>
