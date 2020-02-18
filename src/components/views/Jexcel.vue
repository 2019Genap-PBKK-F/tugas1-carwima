<template>
  <div>
    <div id='Jexcel' ref='spreadsheet'></div>
    <br>
    <div>
      <h1>DAFTAR MAHASISWA</h1>
    </div>
    <div>
      <input type='button' value='Add new row' @click='addRow(spreadsheet)' />
    </div>
    <div>
    This will be the changed message : {{test}}
    </div>
  </div>
</template>

<script>

import jexcel from 'jexcel'
import 'jexcel/dist/jexcel.css'
import Axios from 'axios'

var data = [
  ['17-098', 'Carlo', '2017', '1999-02-12', '', true],
  ['17-098', 'Carlo Win', '2017', '1999-07-11', '', true]
]

var options = {
  data: data,
  allowToolbar: true,
  columns: [
    { type: 'text', title: 'NRP', width: '120px' },
    { type: 'text', title: 'Nama', width: '120px' },
    { type: 'text', title: 'Angkatan', width: '120px' },
    { type: 'calendar', title: 'Tgl Lahir', width: '250px' },
    { type: 'image', title: 'Photo', width: '120px' },
    { type: 'checkbox', title: 'Aktif', width: '80px' }
  ]
}

export default {
  name: 'Jexcel',
  mounted: function() {
    let spreadsheet = jexcel(this.$el, options)
    Object.assign(this, { spreadsheet })
  },
  methods: {
    updateonline: function() {
      Axios.post
    },
    addRow: function(ss) {
      ss.insertRow()
    }
  }
}
</script>
