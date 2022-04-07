<template>
  <footer id="footer">
    <img src="../../public/logo-branco.png" />
    <div class="footer-box-contato"> 
      <div id="sow-editor-3" class="footer-widget">
        <div class="swidget-editor-base">
          <div class="siteorigin-widget">
            <h3>
              <span>Contato:</span>
            </h3>
            <p>
              <br>
              E-mail: contato@elyte.ind.br
              <br>
              Telefone: (51) 9 9886-7720
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
    
    <div class="footer-box"> 
      <div id="sow-editor-3" class="footer-widget">
        <div class="swidget-editor-base">
          <div class="siteorigin-widget">
            <h3>
              <span id="span-local">Localização:</span>
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
.footer-box-contato {
  text-align: left;
  margin: 30px;
}
.span-credits {
  text-align: end;
  color: rgb(255, 255, 255);
}

#span-local {
  padding: 30px;

}
</style>
