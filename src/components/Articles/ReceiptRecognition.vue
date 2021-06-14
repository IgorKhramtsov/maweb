<template>
    <Article title='Receipt recognition algorithm' :year=2018>
      <p class="col-md-10">
        On my internship at IntegraSources, i have implemented a receipt recognition algorithm
        on C++ via OpenCV. The algorithm was able to improve shadow/lights on image, crop it
        to cover the receipt out of background, fixing skew, and detecting text
        via Tesseract engine.
      </p>
      <img src="../../assets/receipts.png" alt="">
      <p class="col-md-10">
        To find and crop receipt on image was used morphology operators,
        after that algorithm applies some denoising and illumination normalization
        algorithms, convert it to grayscale image, then do gamma, brightness and
        contrast correction and add shrapness a little for increasing
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
  components: { Article },
  name: 'ReceiptRecognition',
};
</script>

<style lang="scss" scoped>

</style>
