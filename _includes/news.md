<h2 style="margin: 2px 0px -10px;">
  <a href="./_news/news.html" style="text-decoration: none; color: inherit;">News</a>
</h2>
<br>
<div style="font-size: 16px; line-height: 1.6; letter-spacing: 0.5px; text-align: justify; color: #000000; background-color: #ffffff;">
  <!-- 动态加载新闻内容 -->
  {% for item in site.data.news limit:5 %}
  <p>
    <span style="color: #000;font-weight: 1000;">[</span><span style="color: #d9534f; font-weight: 700; font-family: 'Times New Roman', Times, serif;">{{ item.time }}</span><span style="color: #000;">]</span> {{ item.description }}
  </p>
  {% endfor %}
</div>
