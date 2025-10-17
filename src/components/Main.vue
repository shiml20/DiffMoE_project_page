<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import Markdown from './sections/Markdown.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import Video from './sections/Video.vue'
import ImageSlider from './sections/ImageSlider.vue'
import ImageSliderInner from './sections/ImageSliderInner.vue'
import ImageSelector from './sections/ImageSelector.vue'
import Echart from './sections/Echart.vue'
import Table from './sections/Table.vue'
import Collapse from './sections/Collapse.vue'
import SeletionForComparison from './sections/SeletionForComparison.vue'
import Comment from './sections/Comment.vue'
import Latex from './sections/Latex.vue'
import Model3D from './sections/Model3D.vue'
import GaussianSplats3D from './sections/GaussianSplats3D.vue'

export default {
  components: {
    Title,
    Abstract,
    Markdown,
    BibTeX,
    Carousel,
    Video,
    ImageSlider,
    ImageSliderInner,
    ImageSelector,
    Echart,
    Collapse,
    Table,
    SeletionForComparison,
    Comment,
    Latex,
    Model3D,
    GaussianSplats3D
  },
  data() {
    return {
      navItems: [
        { label: 'Overview', href: '#overview' },
        { label: 'Abstract', href: '#abstract' },
        { label: 'Main Content', href: '#markdown' },
        { label: 'Citation', href: '#bibtex' },
      ]
    }
  }
}
</script>

<template>
  <div class="main-layout">
    <aside class="side-nav">
      <nav>
        <h3>Contents</h3>
        <ul>
          <li v-for="item in navItems" :key="item.href">
            <a :href="item.href">{{ item.label }}</a>
          </li>
        </ul>
      </nav>
    </aside>
    <main class="content-area">
      <section id="overview" class="content-section">
        <Title/>
      </section>
      <!-- <section id="gallery" class="content-section">
        <Carousel/>
      </section> -->
      <!-- <section id="video" class="content-section">
        <Video/>
      </section> -->
      <section id="abstract" class="content-section">
        <Abstract/>
      </section>

      <section id="markdown" class="content-section">
        <Markdown/>

      </section>
      <!-- <section id="latex" class="content-section">
        <Latex/>
      </section>
      <section id="table" class="content-section">
        <Table/>
      </section>
      <section id="collapse" class="content-section">
        <Collapse/>
      </section> -->
      <!-- <section id="echart" class="content-section">
        <Echart/>
      </section>
      <section id="model3d" class="content-section">
        <Model3D/>
      </section>
      <section id="gaussian" class="content-section">
        <GaussianSplats3D/>
      </section> -->
      <!-- <section id="comparison" class="content-section">
        <SeletionForComparison/>
      </section> -->
      <!-- <section id="inner-slider" class="content-section">
        <ImageSliderInner/>
      </section> -->
      <!-- <section id="outer-slider" class="content-section">
        <ImageSlider/>
      </section> -->
      <!-- <section id="selector" class="content-section">
        <ImageSelector/>
      </section> -->
      <section id="bibtex" class="content-section">
        <BibTeX/>
      </section>
      <!-- <section id="comment" class="content-section">
        <Comment/>
      </section> -->
    </main>
  </div>
</template>

<style scoped>
.main-layout {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0px 24px 80px;
  display: flex;
  flex-direction: row;
  gap: 32px;
  align-items: flex-start;
}

.side-nav {
  width: 220px;
  flex-shrink: 0;
  background: #ffffff;
  border-radius: 6px;
  padding: 24px 16px;
  border: none;
  position: sticky;
  top: 20px;
  max-height: calc(100vh - 40px);
  overflow-y: auto;
}

.side-nav h3 {
  font-size: 14px;
  font-weight: 600;
  letter-spacing: 0.3px;
  color: #1a1a1a;
  margin-bottom: 12px;
  text-transform: uppercase;
}

.side-nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.side-nav li a {
  color: #57606a;
  text-decoration: none;
  font-size: 14px;
  line-height: 1.5;
  display: block;
  padding: 4px 8px;
  border-radius: 4px;
  transition: all 0.2s ease;
}

.side-nav li a:hover {
  color: #0969da;
  background: #f6f8fa;
  text-decoration: none;
}

.content-area {
  flex: 1;
  min-width: 0;
  padding: 0;
}

.content-section {
  margin-bottom: 5px;
  padding: 2px 40px;
  background: #ffffff;
  border-radius: none;
  border: none;
}

.content-section:last-of-type {
  margin-bottom: 0;
}

@media (max-width: 992px) {
  .main-layout {
    flex-direction: column;
    padding: 28px 16px 64px;
  }

  .side-nav {
    position: static;
    height: auto;
    width: 100%;
    padding: 22px;
  }

  .content-section {
    padding: 24px;
  }
}

</style>