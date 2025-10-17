<script lang="ts" setup>

import { Document, Files } from '@element-plus/icons-vue'

// logo地址 - SVG logo
// const logo = 'svg/src/assets/logo.svg'
const logo = ''

// 标题 - 不需要，因为在logo中
const title = 'DiffMoE'

// 按钮链接
const buttons = [
  {
    disabled: false,
    name: "arXiv",
    link: "https://huggingface.co/papers/xxx",
    component: Document,
  },
  {
    disabled: false,
    name: "Code",
    link: "https://xxx/",
    component: Files,
  },
]

// 作者信息
const authors = [
  {
    name: "Minglei Shi",
    homepage: "https://github.com/shiml20",
    affiliation: "1",
    marker: "*"
  },
  {
    name: "Haolin Wang",
    homepage: "https://howlin-wang.github.io",
    affiliation: "1",
    marker: "*"
  },
  {
    name: "Wenzhao Zheng",
    homepage: "https://wzzheng.net",
    affiliation: "1",
    marker: "†"
  },
  {
    name: "Ziyang Yuan",
    homepage: "https://scholar.google.ru/citations?user=fWxWEzsAAAAJ&hl=en",
    affiliation: "2",
    marker: ""
  },
  {
    name: "Xiaoshi Wu",
    homepage: "https://scholar.google.com/citations?user=cnOAMbUAAAAJ&hl=en",
    affiliation: "2",
    marker: ""
  },
  {
    name: "Xintao Wang",
    homepage: "https://xinntao.github.io",
    affiliation: "2",
    marker: ""
  },
  {
    name: "Pengfei Wan",
    homepage: "https://scholar.google.com/citations?user=P6MraaYAAAAJ&hl=en",
    affiliation: "2",
    marker: ""
  },
  {
    name: "Jie Zhou",
    homepage: "https://www.imem.tsinghua.edu.cn/info/1330/2128.htm",
    affiliation: "1",
    marker: ""
  },
  {
    name: "Jiwen Lu",
    homepage: "https://www.au.tsinghua.edu.cn/info/1078/3156.htm",
    affiliation: "1",
    marker: ""
  },
]

// 作者注释
const authorNote = "(*equal contribution, listed alphabetically; †project lead)"

// 机构信息
const affiliations = [
  {
    id: "1",
    name: "Department of Automation, Tsinghua University"
  },
  {
    id: "2",
    name: "Kling Team, Kuaishou Technology"
  },
]

</script>

<template>
  <div class="title-section">

    <!-- Logo -->
    <!-- <div class="logo-container">
      <img :src="logo" alt="SVG Logo" class="logo" />
    </div> -->

    <!-- Paper Title -->
    <h1 class="paper-title">{{ title }}</h1>

    <!-- Buttons -->
    <div class="button-container">
      <a :href="button.link" v-for="button in buttons" :key="button.name" class="button-link">
        <button class="guidance-button">
          <component :is="button.component" class="button-icon" />
          <span class="btn-text">{{ button.name }}</span>
        </button>
      </a>
    </div>

    <!-- Authors -->
    <div class="authors-container">
      <a 
        :href="author.homepage" 
        v-for="author in authors" 
        :key="author.name"
        class="author-link"
      >
        <span class="author">
          {{ author.name }}<sup class="name_sup">{{ author.affiliation }}{{ author.marker }}</sup>
        </span>
      </a>
    </div>

    <!-- Author Note -->
    <div class="author-note">
      <small>{{ authorNote }}</small>
    </div>

    <!-- Affiliations -->
    <div class="affiliations-container">
      <div v-for="affiliation in affiliations" :key="affiliation.id" class="affiliation">
        <sup class="affiliation-sup">{{ affiliation.id }}</sup>{{ affiliation.name }}
      </div>
    </div>

  </div>
</template>

<style scoped>

/* Main container */
.title-section {
  text-align: center;
  padding: 30px 0px 20px 0px;
}

/* Logo */
.logo-container {
  margin-bottom: 0px;
}

.logo {
  width: 120px;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

/* Paper Title */
.paper-title {
  font-family: Georgia, "Times New Roman", serif;
  letter-spacing: 0.5px;
  font-size: 48px;
  font-weight: 400;
  margin: 2px 2px 12px;
  text-align: center;
  color: #000000;
}

/* Buttons Container */
.button-container {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin: 0px 0;
}

.button-link {
  text-decoration: none;
}

.guidance-button {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 16px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12);
  background: #ffffff;
  border: 1px solid #d0d7de;
  border-radius: 6px;
  cursor: pointer;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  transition: all 0.2s ease;
}

.guidance-button:hover {
  background: #f6f8fa;
  border-color: #0969da;
}

.button-icon {
  width: 18px;
  height: 18px;
}

.btn-text {
  font-size: 16px;
  color: #1a1a1a;
}

/* Authors Container */
.authors-container {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 4px 16px;
  margin: 12px auto;
  max-width: 900px;
}

.author-link {
  text-decoration: none;
  color: inherit;
}

.author-link:hover .author {
  color: #0969da;
}

.author {
  font-size: 17px;
  color: #1a1a1a;
  transition: color 0.2s ease;
}

.name_sup {
  color: #57606a;
  margin-left: 2px;
}

/* Author Note */
.author-note {
  text-align: center;
  margin: 12px 0;
  color: #57606a;
  font-size: 14px;
}

/* Affiliations Container */
.affiliations-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 8px;
  margin: 12px auto 12px;
  max-width: 700px;
}

.affiliation {
  font-size: 16px;
  color: #1a1a1a;
  text-align: center;
}

.affiliation-sup {
  color: #57606a;
  margin-right: 4px;
}

/* Link styling */
a:-webkit-any-link {
  text-decoration: none;
}

a:hover {
  color: inherit;
  border-bottom: none;
}

a {
  text-decoration: none;
  color: inherit;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .paper-title {
    font-size: 36px;
    margin: 16px;
  }

  .authors-container {
    gap: 8px;
  }

  .author {
    font-size: 15px;
  }

  .button-container {
    flex-direction: column;
    align-items: center;
  }
}

</style>