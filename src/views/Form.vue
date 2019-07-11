<template>
    <div class="mt-5">
        <h1>Formularios</h1>
    <form>
        <b-row>
            <b-col md="3">
                <b-form-input type="text" v-model="texto" :state="comprobar"></b-form-input>
                <small>Mínimo 5 carácteres</small>
                <p>Texto: {{ texto }}</p>
            </b-col>
            <b-col md="3">
                <b-form-select v-model="select" :options="animales"></b-form-select>
                <p>Animal: {{ select }}</p>
            </b-col>
            <b-col md="3">
                <b-form-radio-group v-model="radio" :options="animalesRadio"></b-form-radio-group>
                <p>Animal: {{ radio }}</p>
            </b-col>
            <b-col md="3">
                <b-form-checkbox-group v-model="check" :options="animalesRadio"></b-form-checkbox-group>
                <p>Múltiples datos: {{check}}</p>
            </b-col>
        </b-row>
        </form>

    </div>
</template>


<script>
export default {
    name: 'Form',
    data() {
        return {
            texto: '',
            check: [],
            radio: null,
            select: null,
            animales:[
                {value: null, text: 'Seleccione un animal'},
                {value: 'perro', text: 'Woof woof'},
                {value: 'gato', text: 'Meow meow'},
                {value: 'pato', text: 'Cuack cuack'}
            ],
            animalesRadio: [
                {value: 'perro', text: 'Woof woof'},
                {value: 'gato', text: 'Meow meow'},
                {value: 'pato', text: 'Cuack cuack'}
            ]
        }
    },
    computed: {
        comprobar(){
            return this.texto.length > 4 ? true : false
        }   
    }
}
</script>