<template>
  <div class="container" id="page-text">
    <div class="row">
      <div class="col-sm-10">
        <div class="pix-content pix-padding-bottom-30">
          <Content />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Single'
}
</script>

<style>
#page-text p {
  line-height: 32px;
  margin-top: 2em;
  font-size: 21px;
  letter-spacing: -0.003em;
  margin-bottom: -0.46em;
  word-break: break-word;
}

#page-text h1 {
  margin-top: 1.95em;
  font-weight: 600;
  letter-spacing: -0.022em;
  line-height: 1.12;
  font-style: normal;
  color: rgba(41, 41, 41, 1);
  font-size: 34px;
}
</style>