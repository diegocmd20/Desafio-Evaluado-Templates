<template>
    <div class="container-fluid bg-secondary h-100 w-100">
        <div class="row vh-100 vw-100">
            <div class="col-6 my-auto d-flex flex-column justify-content-center align-items-center">
                <form class="w-50">
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
                    <div class="d-flex align-items-center gap-1 mb-3">
                        <label class="align-self-center">Mostrar Texto</label>
                        <input type="checkbox" class="form-checkbox">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Borde</label>
                        <input v-model="borde" type="range" class="form-range" min="0" max="50">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Contenido Textual</label>
                        <textarea v-model="contenidoTexto" class="form-control" rows="2"
                            placeholder="Ingrese el contenido del texto"></textarea>
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Tipo de Fuente</label>
                        <select v-model="tipoFuente" class="form-select">
                            <option value="italic">Italic</option>
                            <option value="normal">Normal</option>
                            <option value="oblique">Oblicua</option>
                        </select>
                    </div>
                </form>
            </div>
            <div class="col-6 d-flex justify-content-center align-items-center">
                <div :style="{ backgroundColor: colorFondo, borderRadius: borde + '%' }"
                    class="h-50 w-50 d-flex justify-content-center align-items-center text-center">
                    <p :style="{ color: colorTexto, fontStyle: tipoFuente }" class="px-auto py-auto fw-semibold display-6">
                        {{ contenidoTexto }}</p>
                </div>
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
            borde: '',
            contenidoTexto: '',
            tipoFuente: '',
            opaco: '',
            tamanoTexto: '',
        };
    }
};
</script>

<style scoped></style>