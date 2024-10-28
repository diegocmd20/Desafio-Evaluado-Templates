<template>
    <div class="container bg-secondary my-auto mx-auto">
        <div class="row">
            <div class="col-12 col-md-6">
                <form>
                    <div class="mb-3">
                        <label class="form-label">Color de Fondo</label>
                        <input v-model="colorFondo" type="text" class="form-control"
                            placeholder="Ingrese el color de Fondo">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Color de Texto</label>
                        <input v-model="colorTexto" type="text" class="form-control"
                            placeholder="Ingrese el color de Texto">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Contenido Textual</label>
                        <textarea v-model="contenidoTexto" class="form-control" rows="2"
                            placeholder="Ingrese el contenido del texto"></textarea>
                    </div>
                </form>
            </div>
            <div class="col-12 col-md-6 my-auto">
                <p :style="{ color: colorTexto,backgroundColor: colorFondo }">{{ contenidoTexto }}</p>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'Template',
    data() {
        return {
            colorFondo: '',
            colorTexto: '',
            mostrarTexto: '',
            contenidoTexto: '',
            tipoFuente: '',
            opaco: '',
            tamanoTexto: '',
        };
    }
};
</script>

<style scoped></style>