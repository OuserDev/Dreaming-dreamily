<template>
    <loader />
    <button이전 />
    <button다음 />
    <one버튼one v-if="키상태 == 1" />
    <one버튼two v-if="키상태 == 1" />
    <two버튼one v-if="키상태 == 2" />
    <two버튼two v-if="키상태 == 2" />
    <thr버튼one v-if="키상태 == 3" />
    <thr버튼two v-if="키상태 == 3" />
    <four버튼one v-if="키상태 == 4" />
    <four버튼two v-if="키상태 == 4" />
    <fiv버튼one v-if="키상태 == 5" />
    <fiv버튼two v-if="키상태 == 5" />
    <six버튼one v-if="키상태 == 6" />
    <six버튼two v-if="키상태 == 6" />
    <sev버튼one v-if="키상태 == 7" />
    <sev버튼two v-if="키상태 == 7" />
    <eig버튼one v-if="키상태 == 8" />
    <eig버튼two v-if="키상태 == 8" />
    <nin버튼one v-if="키상태 == 9" />
    <nin버튼two v-if="키상태 == 9" />
    <ten버튼one v-if="키상태 == 0" />
    <ten버튼two v-if="키상태 == 0" />
    <div id="app">
        <flipbook class="flipbook" :pages="pages" v-slot="flipbook" :zooms="null" :flipDuration="2000" :centering="true" :dragToFlip="false" :singlePage="false">
            <div v-for="(page, index) in pages" :key="index" class="page">
                <h1>{{ page.title }}</h1>
                <p>{{ page.content }}</p>
            </div>
            <div class="flipbook-head">
                <button이전 @click="flipbook.flipLeft">이전</button이전>
                <button다음 @click="flipbook.flipRight">다음</button다음>
            </div>
        </flipbook>
    </div>
</template>

<script>
import loader from '@/components/loader.vue';
import button이전 from '@/components/이전버튼.vue';
import button다음 from '@/components/다음버튼.vue';
import one버튼one from '@/components/one버튼one.vue';
import one버튼two from '@/components/one버튼two.vue';
import two버튼one from '@/components/two버튼one.vue';
import two버튼two from '@/components/two버튼two.vue';
import thr버튼one from '@/components/thr버튼one.vue';
import thr버튼two from '@/components/thr버튼two.vue';
import four버튼one from '@/components/four버튼one.vue';
import four버튼two from '@/components/four버튼two.vue';
import fiv버튼one from '@/components/fiv버튼one.vue';
import fiv버튼two from '@/components/fiv버튼two.vue';
import six버튼one from '@/components/six버튼one.vue';
import six버튼two from '@/components/six버튼two.vue';
import sev버튼one from '@/components/sev버튼one.vue';
import sev버튼two from '@/components/sev버튼two.vue';
import eig버튼one from '@/components/eig버튼one.vue';
import eig버튼two from '@/components/eig버튼two.vue';
import nin버튼one from '@/components/nin버튼one.vue';
import nin버튼two from '@/components/nin버튼two.vue';
import ten버튼one from '@/components/ten버튼one.vue';
import ten버튼two from '@/components/ten버튼two.vue';
import Flipbook from 'flipbook-vue';

export default {
    components: {
        Flipbook,
        button다음,
        button이전,
        loader,
        one버튼one,
        one버튼two,
        two버튼one,
        two버튼two,
        thr버튼one,
        thr버튼two,
        four버튼one,
        four버튼two,
        fiv버튼one,
        fiv버튼two,
        six버튼one,
        six버튼two,
        sev버튼one,
        sev버튼two,
        eig버튼one,
        eig버튼two,
        nin버튼one,
        nin버튼two,
        ten버튼one,
        ten버튼two,
    },
    name: 'App',
    data: () => {
        return {
            키상태: 0,
            pages: [
                require('@/assets/1-1.png'),
                require('@/assets/1-2.png'),
                require('@/assets/2-1.png'),
                require('@/assets/2-2.png'),
                require('@/assets/3-1.png'),
                require('@/assets/3-2.png'),
                require('@/assets/4-1.png'),
                require('@/assets/4-2.png'),
                require('@/assets/5-1.png'),
                require('@/assets/5-2.png'),
                require('@/assets/6-1.png'),
                require('@/assets/6-2.png'),
                require('@/assets/7-1.png'),
                require('@/assets/7-2.png'),
                require('@/assets/8-1.png'),
                require('@/assets/8-2.png'),
                require('@/assets/9-1.png'),
                require('@/assets/9-2.png'),
                require('@/assets/10-1.png'),
                require('@/assets/10-2.png'),
                require('@/assets/11-1.png'),
                require('@/assets/11-2.png'),
            ],
        };
    },
    methods: {
        handleKeyPress(event) {
            const key = parseInt(event.key, 10);
            if (!isNaN(key) && key >= 0 && key <= 9) {
                this.키상태 = key;
            }
        },
    },
    mounted() {
        window.addEventListener('keydown', this.handleKeyPress);
    },
    beforeDestroy() {
        window.removeEventListener('keydown', this.handleKeyPress);
    },
};
</script>

<style>
#app {
    height: 100vh;
    display: flex;
    align-items: center;
    flex-direction: column;
    overflow: hidden;
    background-color: rgb(255, 255, 255);
    color: #ccc;
}
.flipbook {
    width: 90vw;
    height: 90vh;
}
.flipbook-head {
    text-align: center;
}
#app > div > div.viewport.drag-to-scroll > div > div:nth-child(3) > img:nth-child(1) {
    border-radius: 15px 0 15px 15px;
}
#app > div > div.viewport.drag-to-scroll > div > div:nth-child(3) > img:nth-child(2) {
    border-radius: 0 15px 15px 15px;
}
.bounding-box {
    border-radius: 15px 15px 15px 15px;
    box-shadow: 0 15px 15px rgba(0, 0, 0, 0.5);
}
</style>
