[**Robrix_Worklog_2024_1014**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241014.md)

[**Robrix_Worklog_2024_1015**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241015.md)

[**Robrix_Worklog_2024_1016**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241016.md)

[**Robrix_Worklog_2024_1021**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241021.md)

<script>
  // 获取 Bing 每日图片
  fetch('https://www.bing.com/HPImageArchive.aspx?format=js&idx=0&n=1')
    .then(response => response.json())
    .then(data => {
      const baseUrl = 'https://www.bing.com';
      const imageUrl = baseUrl + data.images[0].url;  // 获取图片的完整URL
      document.body.style.backgroundImage = `url(${imageUrl})`;  // 设置为背景
    })
    .catch(error => console.error('Error fetching Bing image:', error));
</script>
