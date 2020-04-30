<template>
  <q-page padding>
     <q-table
      title="Jadwal Tayang FILM"
      :data="data"
      :columns="columns"
      row-key="name"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="waktu" :props="props">
            {{ props.row.waktu }}
          </q-td>
          <q-td key="judul" :props="props">
            {{ props.row.judul }}
          </q-td>
          <q-td key="keterangan" :props="props">
            {{ props.row.keterangan }}
          </q-td>
          <q-td key="aksi" :props="props">
            <div class="row">
              <div class="col">
                <q-btn label="Pesan" color="green" unelevated></q-btn>
              </div>
              <div class="col">
                <q-btn label="Sinopsis" color="blue" icon="edit" unelevated></q-btn>
              </div>
            </div>
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      columns: [
        {
          name: 'waktu',
          required: true,
          label: 'Waktu',
          align: 'left',
          field: 'waktu',
          sortable: true
        },
        { name: 'judul', align: 'center', label: 'Judul', field: 'judul', sortable: true },
        { name: 'keterangan', label: 'Keterangan', align: 'center', field: 'keterangan', sortable: true },
        { name: 'aksi', label: 'Aksi', field: 'aksi', align: 'center' }
      ],

      data: [
        {
          waktu: '20.30',
          judul: 'Mariposa',
          keterangan: 'romansa'
        },
        {
          waktu: '16.45',
          judul: 'annabelle 3',
          keterangan: 'horror'
        },
        {
          waktu: '22.00',
          judul: 'Dilan & Milea',
          keterangan: 'romansa'
        }
      ]
    }
  }
}
</script>
