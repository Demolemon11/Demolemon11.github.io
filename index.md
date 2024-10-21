[**Robrix_Worklog_2024_1014**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241014.md)

[**Robrix_Worklog_2024_1015**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241015.md)

[**Robrix_Worklog_2024_1016**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241016.md)

[**Robrix_Worklog_2024_1021**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241021.md)


<style>
  body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    height: 100vh;
    background-size: cover;
    background-position: center;
    background-color: #f0f0f0; /* 默认背景色，防止图片加载前页面为空 */
  }
</style>

<script>
  // 从 https://ipgeo-bingpic.hf.space 获取每日 Bing 图片
  fetch('https://ipgeo-bingpic.hf.space')
    .then(response => response.json())
    .then(data => {
      const imageUrl = data.url;  // 获取到图片 URL
      document.body.style.backgroundImage = `url(${imageUrl})`;  // 设置为背景
    })
    .catch(error => console.error('Error fetching Bing image:', error));
</script>
