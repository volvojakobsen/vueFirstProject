<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === sale}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: [ 'theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
    display: flex;
    align-content: center;
    justify-content: center;
    flex-direction: column;
    text-align: center;
}
.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}

.modal h1 {
    color: aqua;
    padding: 0;
}

.modal .actions {
    text-align: center;
    display: flex;
    flex-direction: column;
}

.modal.sale {
    background: aqua;
    color: aliceblue;
}
</style>