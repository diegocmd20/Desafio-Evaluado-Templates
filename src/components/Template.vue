<template>
    <div class="container-fluid bg-secondary h-100 w-100">
        <div class="row vh-100 vw-100">
            <div class="col-6 my-auto d-flex flex-column justify-content-center align-items-center">
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
                    <div class="form-check mb-3">
                        <label class="form-check-label">Mostrar Texto</label>
                        <input type="checkbox" class="form-check-input" v-model="mostrarTexto">
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
                        <select v-model="fuenteSeleccionada" class="form-select">
                            <option v-for="fuente in fuentes" :value="fuente" :key="fuente.nombre">{{fuente.nombre}}</option>
                        </select>
                    </div>
                    <div class="d-flex align-items-center gap-1 mb-3">
                        <label class="align-self-center">Opaco</label>
                        <input type="checkbox" class="form-check-input" v-model="opaco">
                    </div>
                    <div class="mb-3">
                        <label class="form-label">Tamaño de Letra</label>
                        <div class="mb-3">
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" v-model="tamanoTexto"
                                    value="px-auto py-auto fw-semibold fs-6 text">
                                <label class="form-check-label">
                                    Pequeño
                                </label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" v-model="tamanoTexto"
                                    value="px-auto py-auto fw-semibold fs-3 text">
                                <label class="form-check-label">
                                    Mediano
                                </label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" v-model="tamanoTexto"
                                    value="px-auto py-auto fw-semibold fs-1 text">
                                <label class="form-check-label">
                                    Grande
                                </label>
                            </div>
                        </div>
                    </div>
                </form>
            </div>
            <div class="col-6 d-flex justify-content-center align-items-center">
                <div :style="{ backgroundColor: colorFondo, borderRadius: borde + '%', opacity: opaco === true? 0.5 : 1 }"
                    class="h-50 w-50 d-flex justify-content-center align-items-center text-center"
                    v-if="mostrarTexto === true">
                    <p :style="{color: colorTexto}" :class="[tamanoTexto, fuenteSeleccionada.estiloTexto]">
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
            mostrarTexto: false,
            borde: '',
            contenidoTexto: '',
            fuenteSeleccionada: {},
            fuentes: [
                {
                    nombre: 'Italic',
                    estiloTexto: 'fst-italic',
                },
                {
                    nombre: 'Normal',
                    estiloTexto: 'fst-normal',
                },
                {
                    nombre: 'Tachado',
                    estiloTexto: 'text-decoration-line-through',
                },
                {
                    nombre: 'Subrayado',
                    estiloTexto: 'text-decoration-underline',
                }
            ],
            opaco: false,
            tamanoTexto: '',
        };
    }
};
</script>

<style scoped></style>