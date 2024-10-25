<template>
    <Head>
        <title>About to laravel + quasar</title>
    </Head>
    <Hero />
    <Layout>   
        <q-page class="column flex-center">

            <h1>Wooo Page</h1>
            <div class="q-pa-md grid items-start q-gutter-md">
                <q-card class="my-card">
                    <img src="https://heckin-snackers.web.app/images/products/2.jpg">

                    <q-card-section>
                        <div class="text-h6">Our Changing Planet</div>
                        <div class="text-subtitle2">by John Doe</div>
                    </q-card-section>

                    <q-card-section class="q-pt-none">
                        {{ lorem }}
                    </q-card-section>
                </q-card>
            </div>  

            <div class="flex q-gutter-lg justify-center items-center">
                <q-img
                    width="100px"
                    fit
                    src="https://cdn.quasar.dev/logo-v2/svg/logo.svg"
                    alt="Quasar Logo"
                />
                <q-icon name="favorite" color="red" size="50px" />
                <q-img
                    fit
                    width="100px"
                    src="https://laravel.com/img/logomark.min.svg"
                    alt="Laravel Logo"
                />
            </div>

         
            
            <div class="q-mt-xl">
                <q-btn
                    color="primary"
                    dense
                    round
                    label="-"
                    :disable="count === min"
                    @click="count--"
                />

                <span class="q-mx-md text-bold">{{ count }}</span>                <q-btn
                    color="primary"
                    dense
                    round
                    label="+"
                    :disable="count === max"
                    @click="count++"
                />
            </div>

            <div class="q-mt-md" style="width: 200px">
                <q-slider v-model="count" :min="min" :max="max" />
            </div>

            <div>
                <q-toggle label="Dark Mode" v-model="darkMode" />
            </div>
        </q-page>
    </Layout>
</template>
<script setup>
import Layout from "../layouts/MainLayout.vue";
import { ref, watch } from "vue";
import { Head } from "@inertiajs/vue3";
import { Dark } from "quasar";
import Hero from "../components/Hero.vue";

const count = ref(0);
const min = -5;
const max = 5;

const darkMode = ref(Dark.isActive);
watch(darkMode, (value) => {
    Dark.set(value);
});
</script>
