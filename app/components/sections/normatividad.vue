<script>
import DocumentButton from '../documentButton.vue';

</script>


<template>
  <div class="grid grid-flow-col sm:grid-cols-2 lg:grid-cols-5 justify-items-center gap-4">
    <DocumentButton [title]="1" name="Constancia IFT Cobertura" document="CONSTANCIA-IFT-COBERTURA.pdf">
    </DocumentButton>

    <DocumentButton [title]="2" name="Derechos del usuario" document="DERECHOS-DEL-USUARIO.pdf"></DocumentButton>

    <DocumentButton [title]="3" name="Constancia IFT nombre comercial" document="CONSTANCIA-IFT-NOMBRE-COMERCIAL.pdf">
    </DocumentButton>

    <DocumentButton [title]="4" name="Prácticas comerciales" document="PRACTICAS-COMERCIALES.pdf"></DocumentButton>

    <DocumentButton [title]="5" name="Contrato de adhesión" document="CONTRATO_ADHESION.docx"></DocumentButton>
  </div>

</template>

<style></style>
