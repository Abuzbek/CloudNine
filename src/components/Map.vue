<template>
  <div class="mainWrapper">
    <div class="mapWrapper">
      <div id="map"></div>
    </div>
    <div class="infoBlock flex ">
      <div class="phone">
        <img :src="phoneIcon" alt="" />
        <span>+998 98 765 43 21</span>
      </div>
      <div class="location">
        <img :src="locationIcon" alt="" />
        <span>Mo`ljal Huvaydo restorani</span>
      </div>
    </div>
  </div>
</template>

<script>
import { Loader } from 'google-maps';
import phoneIcon from '../assets/MapIcons/telephone.png';
import locationIcon from '../assets/MapIcons/Group.png';

const loader = new Loader('AIzaSyA87hHCCB5xPl-8ZnSYm8UBr0COGtNKPOs');


export default {
  name: 'Map',
  data() {
    return {
      map: null,
      office: { lat: 41.340097, lng: 69.204063 },
      marker: null,
      phoneIcon,
      locationIcon,
    };
  },
  async created() {
    const google = await loader.load();
    this.map = new google.maps.Map(document.getElementById('map'), {
      center: this.office,
      zoom: 18,
    });
    this.marker = new google.maps.Marker({
      position: this.office,
      map: this.map,
    });

  },
};
</script>

<style scoped lang="scss">
  #map {
    height: 100%;
    outline: none;
  }


  .mapWrapper {
    height: 89%;
  }

  .mainWrapper {
    height: 100%;
  }

  .infoBlock {
    padding: 1% 10%;
    background: #fff;
    display: flex;
    flex-wrap: nowrap;
    height: 11%;
    align-items: center;
    justify-content: space-between;
  }

  .phone,
  .location {
    width: 45%;
    display: flex;
    align-items: center;

    span {
      margin-left: 10%;
      font-family: Segoe UI;
      font-size: 18px;
      line-height: 24px;
    }
  }
</style>