<template>
    <div class="modalbg">
        <div class="modal" :class="{ sale: theme === 'sale' }">
            <h1>{{ header }}</h1>
            <p>modal content</p>
            <ul>
                <li v-for="i in arr" :key="i">
                    <p>{{ i }}</p>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['header', 'arr', 'theme']
    }
    
</script>

<style scoped>
    .modalbg {
        background: rgba(0,0,0, 0.2);
        position: fixed;
        top: 0;
        width: 100%;
        height: 100%;
        margin: auto;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    p {
    color: orange
    }

    .sale {
        background: red !important;
    }

    .modal {
        padding: 40px;
        background: white;
        border-radius: 20px;
        margin: auto;
    }
</style>