<template>
    <div
      class="m-map"
      :id="id"
      :style="{width:width+'px',height:height='px',margin:'34px auto'}"/>
</template>

<script>
    export default {
      props: {
        width: {
          type: Number,
          default: 300
        },
        height: {
          type: Number,
          default: 300
        },
        point: {
          type: Array,
          default(){
            return [116.46,39.92]
          }
        }
      },
      data() {
        return {
          id: 'map',
          key: '0dbc0dfd7c775f2a927174493eab8220'
        }
      },
      watch: {
        point: function (val, old) {
          this.map.setCenter(val)
          this.marker.setPosition(val)
        }
      }
    }
</script>


