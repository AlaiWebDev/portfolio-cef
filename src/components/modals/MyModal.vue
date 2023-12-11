<script setup>
    import { ref }  from 'vue'
    import { onClickOutside } from '@vueuse/core'
    const props = defineProps({
        isOpen: Boolean,
        toDisplay: Number,
        jobs: Array
    });
    const emit = defineEmits(["modal-close"]);
    const target = ref(null)
    onClickOutside(target, () => emit('modal-close'))
</script>

<template>
    <div v-if="isOpen" class="modal-mask">
    
    <div class="modal-wrapper">
        <div class="modal-container" ref="target">
            <div class="modal-header">
                <slot name="header"> {{ jobs[toDisplay].nom }} </slot>
            </div>
            <div class="modal-body">
                <slot name="content">
                    <img :src="`../../public/${jobs[toDisplay].image}.jpg`" :alt="`${jobs[toDisplay].image}`">
                    <p v-if="jobs[toDisplay].apprenants">{{ jobs[toDisplay].apprenants }} apprenants</p>
                    <p>Période : {{ jobs[toDisplay].date }}</p>
                </slot>
            </div>
            <div class="modal-footer">
                <slot name="footer">
                    <div>
                        <button @click.stop="emit('modal-close')">Fermer</button>
                    </div>
                </slot>
            </div>
        </div>
    </div>
  </div>
</template>
<style scoped>
p {
    color: #010440;
}
.modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
}
.modal-container {
    width: 400px;
    margin: 150px auto;
    padding: 20px 30px;
    text-align: center;
    background-color: #fff;
    border-radius: 2px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
}
.modal-header{
    color: #010440;
}
button {
    display: block;
    width: fit-content;
    margin: auto;
    padding: .5rem;
    color: #010440;
}
</style>