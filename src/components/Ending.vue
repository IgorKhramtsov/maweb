<template>
    <section class="container-fluid">
        <span>THE VOID</span>
        <img src="../assets/milkcat.png" alt="cat drinks milk">
    </section>
</template>

<script>
export default {
  name: 'Ending',
};
</script>

<style lang="scss" scoped>
section {
    position: relative;
    display: block;
    padding-top: 80px;
    padding-bottom: 40px;
}
span {
    font-weight: 200;
    font-size: 22.898px;
    line-height: 27px;
    letter-spacing: 0.471em;

    padding: 5px 30px;
    padding-right: 22px;
    text-align: center;
    border: #e2e2e2 1px solid;
}
img {
    position: absolute;
    display: block;
    bottom: 0px;
    right: 0px;
}
</style>
