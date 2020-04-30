<template>
    <q-page padding>
        <q-card flat >
            <q-card-section class="q-gutter-md">
                <div class="text-h5">Input FILM</div>
                <q-form
                @submit="onSubmit"
                @reset="onReset"
                class="q-mt-lg"
                >
                    <div class="q-gutter-md">
                        <q-input label="Waktu" v-model="waktu" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Waktu']"></q-input>
                        <q-input label="Judul Kegiatan" v-model="judul" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Judul']"></q-input>
                        <q-input label="Keterangan" v-model="keterangan" filled :rules="[ val => val && val.length > 0 || 'Silahkan Isi Keterangan']"></q-input>
                        <q-btn type="submit" label="Input" color="grey" unelevated></q-btn>
                        <q-btn type="reset" label="Reset" color="grey" flat unelevated></q-btn>
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
        message: 'Berhasil Input FILM yang sedang tayang'
      })
      this.$router.push({ name: 'dashboard' })
    }
  }
}
</script>
