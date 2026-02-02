<h2 style="margin: 2px 0px -10px;">
  <a href="./_publication/publication.html" style="text-decoration: none; color: inherit;">Publications</a>
</h2>
<br>

<div class="publications" style="max-width: 900px; margin: auto; font-size: 14px; line-height: 1.5;">
  <ol class="bibliography" style="padding-left: 0; margin-bottom: 3px;">
    {% for link in site.data.publications.main %}
    <li style="list-style: none; margin-bottom: 10px;">
      <div class="pub-row" style="display: flex; flex-wrap: wrap; align-items: stretch; min-height: 140px; background-color: #f8f9fa; box-shadow: 0 4px 12px rgba(0,0,0,0.1); border-radius: 8px; padding: 10px 20px;">
        
  <!-- 左侧图片区域 -->
  <div class="col-sm-3 abbr" style="flex: 0 0 25%; padding-right: 20px; display: flex; align-items: flex-start; justify-content: center; height: 140px; position: relative;">
    {% if link.image %}
    <img src="{{ link.image }}" style="max-height: 100%; max-width: 100%; object-fit: contain; border-radius: 4px;">
    {% if link.venue %}
    <div class="venue-tag" style="position: absolute; top: 0; left: 0; background-color: #0056b3; color: white; padding: 4px 8px; font-size: 12px; font-weight: 600; border-radius: 4px 0 4px 0; z-index: 10;">
      {{ link.venue }}
    </div>
    {% endif %}
    {% endif %}
  </div>
  
  <!-- 右侧内容区域 -->
  <div class="col-sm-9" style="flex: 1;">
    <div class="title" style="font-weight: 600; font-size: 19px; color: #000000;font-family: 'Times New Roman', Times, serif;">
      {% if link.pdf %}
      <a href="{{ link.pdf }}" style="color: #3498db; text-decoration: none;">{{ link.title }}</a>
      {% else %}
      {{ link.title }}
      {% endif %}
    </div>
    <div class="author" style="margin-top: 8px; font-size: 14px; color: #000000;font-family: 'Times New Roman', Times, serif;">{{ link.authors }}</div>
    <div class="periodical" style="margin-top: 6px; font-style: italic; font-size: 14px; color: #000000;font-family: 'Times New Roman', Times, serif;">{{ link.conference }}</div>
    
  <!-- 按钮区域 -->
  <div class="links" style="margin-top: 10px; display: flex; flex-wrap: wrap; gap: 8px;">
    {% if link.abstract %}
    <button onclick="toggleContent(this, 'abstract')" style="font-size: 12px; padding: 3px 8px; background-color: #0056b3; color: white; border: none; border-radius: 3px; cursor: pointer;">
      Abstract
    </button>
    {% endif %}
    {% if link.bibtex %}
    <button onclick="toggleContent(this, 'bibtex')" style="font-size: 12px; padding: 3px 8px; background-color: #0056b3; color: white; border: none; border-radius: 3px; cursor: pointer;">
      BibTex
    </button>
    {% endif %}
    {% if link.pdf %}
    <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size: 14px; padding: 3px 8px; background-color: #0056b3; color: white; border: none; border-radius: 3px; text-decoration: none;">PDF</a>
    {% endif %}
    {% if link.code %}
    <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size: 14px; padding: 3px 8px; background-color: #0056b3; color: white; border: none; border-radius: 3px; text-decoration: none;">GitHub</a>
    {% endif %}
  </div>
  
  <!-- Abstract 内容（默认隐藏） -->
  {% if link.abstract %}
  <div class="abstract-content" style="display: none; margin-top: 10px; margin-right: 15px; background: #eef3f7; padding: 8px 10px; border-radius: 4px; font-size: 14px; line-height: 1.4; text-align: justify; color: #000000; font-family: 'Times New Roman', Times, serif;">
    {{ link.abstract }}
  </div>
  {% endif %}
  
  <!-- BibTex 内容（默认隐藏） -->
  {% if link.bibtex %}
  <pre class="bibtex-content" style="display: none; margin-top: 5px; margin-right: 15px; background: #eef3f7; padding: 8px 10px; border-radius: 4px; font-size: 14px; line-height: 1.4; white-space: pre-wrap; font-family: 'Times New Roman', Times, serif;">{{ link.bibtex }}</pre>
  {% endif %}
  </div>
</div>
</li>
{% endfor %}
  </ol>
</div>

<script>
function toggleContent(button, type) {
  const parent = button.closest('.col-sm-9');
  const content = parent.querySelector('.' + type + '-content');
  
  if (content.style.display === 'none') {
    content.style.display = 'block';
    button.textContent = type === 'abstract' ? 'Hide Abstract' : 'Hide BibTex';
  } else {
    content.style.display = 'none';
    button.textContent = type === 'abstract' ? 'Abstract' : 'BibTex';
  }
}
</script>
