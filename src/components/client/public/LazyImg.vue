<template>
    <!--
       <img :src="url" :width="size.width" :height="size.height" :class="imgClass" :data-index="dataIndex" />
     -->
    <img src="../../../assets/images/loading.jpg" :width="size.width" :class="imgClass" :data-index="dataIndex" />
</template>

<script>
export default {
    props: ['src', 'imgClass', 'dataIndex','size'],
    data() {
        return {
            url: '../../../assets/images/loading.jpg'
        }
    },
    mounted() {
        // let tempImg = new Image();
        // tempImg.src = this.src;
        // tempImg.onerror = _ => {
        //     tempImg.src = "../../../assets/images/space.jpg"
        // };
        // tempImg.onload = () => {
        //     this.url = tempImg.src;
        // }
    }
}
</script>

<style lang="scss" scoped>
</style>