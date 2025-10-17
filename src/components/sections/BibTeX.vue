<script>
export default {
  data() {
    return {
      bibtex: [
        "@inproceedings{svg2026,",
        "    title={SVG: Scalable Vector Generation for High-Quality Images},",
        "    author={Author One and Author Two and Author Three and Author Four},",
        "    booktitle={International Conference on Learning Representations (ICLR)},",
        "    year={2026}",
        "}",
      ],
      copyMessage: ''
    }
  },
  methods: {
    copyVal() {
      let oInput = document.createElement('textarea');
      let text = document.getElementById('bibtex').innerText;
      oInput.value = text;
      document.body.appendChild(oInput);
      oInput.select();
      document.execCommand('Copy');
      this.copyMessage = 'Copied!';
      oInput.remove();
      setTimeout(() => {
        this.copyMessage = '';
      }, 2000);
    }
  }
}

</script>

<template>
  <div>
    <hr class="divider" />
      
    <div class="section-header">
      <h1 class="section-title">BibTeX</h1>
    </div>
    
    <div class="bibtex-container">
      <div class='bibtex' @click="copyVal()">
        <div class="copy-hint">
          🖱️ Click here to copy BibTeX.
          <span v-if="copyMessage" class="copy-success">{{ copyMessage }}</span>
        </div>
        <div class="code-wrapper">
          <pre id="bibtex"><code v-for="b in bibtex" :key="b">{{ b }}<br/></code></pre>
        </div>
      </div>
    </div>

  </div>
</template>

<style scoped>

.section-header {
  text-align: center;
}

.bibtex-container {
  display: flex;
  justify-content: center;
  margin: 0 auto;
  max-width: 800px;
}

/* 卡片属性 */
.bibtex {
  margin: 20px 0px;
  padding-top: 5px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12);
  border-radius: 6px;
  cursor: pointer;
  transition: all 0.3s ease;
  width: 100%;
  border: none;
}

/* 卡片悬浮 */
.bibtex:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  transform: translateY(-2px);
}

/* 卡片点击 */
.bibtex:active{
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12);
  transform: translateY(0);
}

.copy-hint {
  text-align: center;
  color: #57606a;
  margin-top: 20px;
  font-size: 14px;
}

.copy-success {
  color: #0969da;
  font-weight: 600;
  margin-left: 10px;
}

.code-wrapper {
  margin: 0px 20px 5px 20px;
  max-height: 400px;
  overflow-y: auto;
}

pre {
  border: none;
  border-radius: 0px;
  padding: 10px;
  background: none;
}

pre code {
  font-size: 16px;
  background: #ffffff;
}

</style>