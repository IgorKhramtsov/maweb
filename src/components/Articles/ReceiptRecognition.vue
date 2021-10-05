<template>
  <Article title="Receipt recognition algorithm" year="2018" repoUrl="http://github.com/IgorKhramtsov/receipt-recognition">
    <p class="col-md-10">
      On an internship at IntegraSources, I've implemented a receipt recognition algorithm
      on C++ and OpenCV. The algorithm was able to tune shadows/lights on image, crop it
      to cover the receipt only, fixing skew, and detecting text via Tesseract engine.
    </p>
    <img src="../../assets/receipts.png" alt="algorithm scheme">
    <p class="col-md-10">
      To find and crop receipt on image was used morphology operators,
      after that algorithm applies some denoising and illumination normalization
      algorithms, convert it to grayscale image, then do gamma, brightness and
      contrast correction and add a little bit of shrapness to increase
      symbols readdability. After all visual changes&nbsp;-&nbsp;algorithm convert image
      to black and white image by adaptive threshold, and perform deskewing.
      Then perform few more morphology operators to select all text areas
      and perform OCR on them.
    </p>
  </Article>
</template>

<script>
import Article from '../Article.vue';

export default {
  name: 'ReceiptRecognition',
  components: { Article },
};
</script>

<style lang="scss" scoped>

</style>
