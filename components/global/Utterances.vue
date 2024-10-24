<template>
    <div ref="utterancesContainer"></div>
  </template>
  
  <script>
  export default {
    mounted() {
      const script = document.createElement('script');
      script.src = 'https://utteranc.es/client.js';
      script.setAttribute('repo', 'FiorellaBonilla/Tarea2Comentarios');  
      script.setAttribute('issue-term', 'pathname');  
      script.setAttribute('theme', 'github-light');  
      script.setAttribute('crossorigin', 'anonymous');
      script.setAttribute('async', true);
  
      this.$refs.utterancesContainer.appendChild(script);
    }
  }
  </script>
