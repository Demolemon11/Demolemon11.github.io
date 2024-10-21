[**Robrix_Worklog_2024_1014**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241014.md)

[**Robrix_Worklog_2024_1015**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241015.md)

[**Robrix_Worklog_2024_1016**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241016.md)

[**Robrix_Worklog_2024_1021**](https://github.com/Demolemon11/Demolemon11.github.io/blob/hotfix/work_logs/robrix_worklog_20241021.md)

<script>
  // 使用 bing.biturl.top API 来获取 1920x1080 分辨率的 Bing 图片
  fetch('https://bing.biturl.top/?resolution=1920&format=json')
    .then(response => response.json())
    .then(data => {
      const imageUrl = data.url;  // 获取到 1920x1080 分辨率的图片 URL
      document.body.style.backgroundImage = `url("${imageUrl}")`;
    })
    .catch(error => console.error('Error fetching Bing image:', error));
</script>
