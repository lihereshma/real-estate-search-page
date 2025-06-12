<template>
  <section class="map-container" ref="mapContainer">
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d52918450.40025157!2d-161.85240697328845!3d35.94976132466603!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x54eab584e432360b%3A0x1c3bb99243deb742!2sUnited%20States!5e0!3m2!1sen!2sin!4v1749695328278!5m2!1sen!2sin" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
  </section>
</template>

<script>
export default {
  name: 'LocationMap'
}
</script>

<style>
.map-container {
  width: 50%; /* Fixed width for map */
  height: 80vh;
  overflow: hidden; /* Prevent scroll in map section */
  position: sticky; /* Optional if you want it to scroll with page */
  top: 0;
}

.map-container iframe {
  width: 100%;
  height: 100%;
}

/* Mobile style - map collapsed behind or smaller */
@media (max-width: 768px) {
  .map-container {
    width: 100%;
    height: 180px;
    margin-bottom: 1rem;
    display: none;
  }
}
</style>