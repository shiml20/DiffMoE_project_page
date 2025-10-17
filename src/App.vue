<script>

import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'

export default {
  components: {
    Header,
    Main,
    Footer,
  },
  data() {
    return {
      showBackToTop: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.showBackToTop = window.scrollY > 300
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
  }
}

</script>

<template>
    <div class="app-wrapper">
      <!-- <Header/> -->
      <Main/>
      <!-- <Footer/> -->
      
      <!-- 回到顶部按钮 -->
      <button 
        class="back-to-top" 
        @click="scrollToTop"
        v-show="showBackToTop"
      >
        ↑
      </button>
    </div>
</template>

<style>

html {
  scroll-behavior: smooth;
}

body {
  background-color: #ffffff;
  color: #1a1a1a;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
  line-height: 1.6;
}

h1 {
  font-family: Georgia, "Times New Roman", serif;
  letter-spacing: 0.5px;
  font-size: 32px;
  font-weight: 400;
  margin: 0px;
  text-align: center;
  color: #000000;
}

h2, h3, h4, h5, h6 {
  font-family: Georgia, "Times New Roman", serif;
  letter-spacing: 0.3px;
  font-weight: 400;
  color: #1a1a1a;
}

p, li {
  font-size: 17px;
  line-height: 1.7;
  color: #333333;
}

code {
  font-family: 'Monaco', 'Consolas', monospace;
  border-radius: 3px;
  padding: 2px 6px;
  background: #f6f6f6;
  color: #24292e;
  font-size: 0.9em;
}

pre {
  border-radius: 4px;
  padding: 16px;
  background: #f6f6f6;
  line-height: 1.5;
  color: #24292e;
  border: 1px solid #e1e4e8;
}

pre:not(pre[id=bibtex]) {
  overflow-x: auto;
}

pre code {
  font-size: 14px;
  color: #24292e;
  border: none;
  padding: 0px;
  background: transparent;
}

blockquote {
  border-left: 3px solid #d0d7de;
  padding: 12px 24px;
  margin: 16px 0;
  background: #f6f8fa;
  color: #24292e;
}

blockquote > p {
  margin-block-start: 0.5em;
  margin-block-end: 0.5em;
}

/* 链接颜色装饰 */
a {
  color: #0969da;
  text-decoration: none;
}

/* 鼠标焦点悬浮在链接上的颜色装饰 */
a:hover {
  color: #0550ae;
  text-decoration: underline;
}

p > img {
  width: 80%;
  display: block;
  margin: 0 auto;
  border-radius: 4px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12);
}

table {
  border-collapse: collapse;
  width: max-content;
  max-width: 100%;
  margin: 0 auto;
  display:block;
  overflow-x:auto;
  background-color: #ffffff;
}

thead {
  border-bottom-width: 1px;
  border-top-width: 1px;
  border-left-width: 0px;
  border-right-width: 0px;
  border-style: solid;
  border-color: #d0d7de;
}

tbody tr:last-child {
  border-bottom-width: 1px;
  border-top-width: 0px;
  border-left-width: 0px;
  border-right-width: 0px;
  border-style: solid;
  border-color: #d0d7de;
}

th, td {
    padding-left: 1rem;
    padding-right: 1rem;
}

.katex-display {
  overflow-x: auto;
  overflow-y: hidden;
}

/* Divider styling */
.divider {
  border: 0;
  border-top: 1px solid #d0d7de;
  margin: 24px 0;
}

/* Section title styling */
.section-title {
  font-family: Georgia, "Times New Roman", serif;
  font-size: 28px;
  font-weight: 400;
  color: #1a1a1a;
  margin: 24px 0;
}

/* App wrapper */
.app-wrapper {
  min-height: 100vh;
}

/* 回到顶部按钮 */
.back-to-top {
  position: fixed;
  right: 40px;
  bottom: 80px;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: #ffffff;
  border: 1px solid #d0d7de;
  color: #1a1a1a;
  font-size: 20px;
  cursor: pointer;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
  transition: all 0.3s ease;
  z-index: 1000;
}

.back-to-top:hover {
  background: #f6f8fa;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  transform: translateY(-2px);
}

.back-to-top:active {
  transform: translateY(0);
}

</style>