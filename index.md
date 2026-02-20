---
layout: page
---

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  const lang = navigator.language || navigator.userLanguage || ''
  if (lang.startsWith('zh')) {
    window.location.replace('/zh/')
  } else {
    window.location.replace('/en/')
  }
})
</script>

<div style="display: flex; justify-content: center; align-items: center; min-height: 50vh; gap: 2rem;">
  <a href="/zh/" style="font-size: 1.2rem;">中文文档</a>
  <a href="/en/" style="font-size: 1.2rem;">English Docs</a>
</div>
