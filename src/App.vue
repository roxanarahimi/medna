<template>
    <div ref="pdfContent" id="contentToPrint">
      <div class="parallax">
        <the-navbar />
        <img src="/img/header1.png" class="w-100" alt="">
      </div>
      <main class="container-fluid px-5">
        <router-view/>
      </main>
     <the-footer />
  </div>
</template>

<script>
import TheNavbar from './components/TheNavbar';
import TheFooter from './components/TheFooter';
import html2pdf from 'html2pdf.js';

export default {
  components: {TheNavbar, TheFooter},
  name: 'PrintToPdf',
  methods: {
    pdf() {
      const element = document.querySelector('#contentToPrint');  // Reference to the content to print
      const options = {
        margin: 0,
        filename: 'document.pdf',
        image: {type: 'jpg', quality: 1},
        html2canvas: {scale: 3},
        jsPDF: {
          format: 'a2', orientation: 'portrait', compress: true
        },

      };

      html2pdf().set(options).from(element).toPdf().save();


    }
  }
}

</script>
<style>

nav a {
  color: maroon !important;

}

nav a.router-link-exact-active {
  color: maroon !important;
  font-weight: bolder !important;
}

</style>
