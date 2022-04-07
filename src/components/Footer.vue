<template>
  <footer id="footer">
    <img src="../../public/logo-branco.png" />
    <span class="span-ceredits">Desenvolvimento: Departamento de TI - Fundimisa © 2020</span> <br>
    <div class="footer-box"> 
      <div id="sow-editor-3" class="footer-widget">
        <div class="swidget-editor-base">
          <div class="siteorigin-widget">
            <h3 style="text-align: right;">
              <span style="text-align: right;">Localização:</span>
            </h3>
            <p>
              <br>
              Rodovia BR 285, km 503,5, s/n°
              <br>
              Bairro Interior
              <br>
              Cidade: Entre-Ijuis/RS
              <br>
              CEP:98.855-000
              <br>
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="footer-box1"> 
      <div id="sow-editor-2" class="footer-widget1">
        <div class="swidget-editor-base1">
          <div class="siteorigin-widget1">
            <h3 style="text-align: left;">
              <span style="text-align: left;">Contato:</span>
            </h3>
            <p>
              <br>
              Rodovia BR 285, km 503,5, s/n°
              <br>
              Bairro Interior
              <br>
              Cidade: Entre-Ijuis/RS
              <br>
              CEP:98.855-000
              <br>
            </p>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
}
  
</script>

<style scoped>
#footer {
  height: 200px;
  background-color: #222;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  
}

#sow-editor-3{
   text-align: right;
}

.span-ceredits {
  text-align: end;
  color: rgb(255, 255, 255);
}
</style>
