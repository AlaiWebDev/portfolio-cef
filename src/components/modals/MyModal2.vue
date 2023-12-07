<script setup>
    import { defineProps, defineEmits, ref }  from 'vue'
    import { onClickOutside } from '@vueuse/core'
    const jobs = ref([
        {
            nom: "DWWM-ID-Formation-Strasbourg",
            date: "03/2022-11/2022",
            apprenants: 12,
            image: "work-1"
        },
        {
            nom: "DWWM-AFPA-Angers",
            date: "09/2023-09/2023",
            apprenants: 11,
            image: "work-2"
        },
        {
            nom: "DWWM-AFPA-Marseille",
            date: "09/2023-11/2023",
            apprenants: 17,
            image: "work-3"
        },
    ])
    const props = defineProps({
        isOpen: Boolean,
        workItem: Object

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
                <slot name="header"> {{ workItem.nom }} </slot>
            </div>
            <div class="modal-body">
                <slot name="content">
                    <img :src="`../../public/${workItem.image}.jpg`" :alt="`${workItem.image}`">
                    <p>{{ workItem.apprenants }} apprenants</p>
                    <p>Période : {{ workItem.date }}</p>
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
.modal-header {

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