<h2 style="margin: 2px 0px -10px;">
  <a href="./_news/news.html" style="text-decoration: none; color: inherit;">News</a>
</h2>
<br>
<div style="font-size: 16px; line-height: 1.6; letter-spacing: 0.5px; text-align: justify;">
  <!-- 动态加载新闻内容 -->
  {% for item in site.data.news limit:5 %}
  <p>
    - <span style="color: #d9534f; font-weight: bold;">{{ item.time }}</span>: {{ item.description }}
  </p>
  {% endfor %}
  
  <p style="font-size: 16px; text-align: center; margin-bottom: 0px;">
    <a href="./_news/news.html" style="text-decoration: underline; color: #888;">
      - 🔺 more -
    </a>
  </p>
</div>
