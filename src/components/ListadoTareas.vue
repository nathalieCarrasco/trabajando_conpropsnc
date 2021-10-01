<template>
<div >
<li >{{ tareaNueva }} 
    <button v-on:click="$emit('eliminarTarea')">Eliminar</button>
</li> 
</div>
</template>

<script>

export default {
name: 'ListadoTarea',

    props: {
        tareaNueva: {
        type: String,
    },
},
}
</script>