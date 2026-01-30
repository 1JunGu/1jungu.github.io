---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Now, I'm a postdoctoral researcher in Fudan University, working with Prof. [Jiacan Yuan](http://yuanjiacan.com/)

I received my Ph.D. in geophysics from USTC in June 2025, advised by Prof. [Chun Zhao](https://aemol.ustc.edu.cn/member/list/0/)

I received my B.S. in atmospheric science from USTC in June 2020.

<style>
.news-container {
  max-width: 800px;
}
.news-item {
  padding: 12px 0;
  border-bottom: 1px solid #eee;
  display: flex;
  align-items: flex-start;
  gap: 12px;
  animation: fadeIn 0.5s ease-in-out;
}
.news-item:last-child {
  border-bottom: none;
}
.news-badge {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 4px 10px;
  border-radius: 15px;
  font-size: 0.8em;
  font-weight: 600;
  white-space: nowrap;
  box-shadow: 0 2px 4px rgba(102, 126, 234, 0.3);
}
.news-badge.new {
  background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
  animation: pulse 2s infinite;
}
.news-content {
  flex: 1;
  line-height: 1.6;
}
.news-hidden {
  display: none;
}
.news-toggle {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border: none;
  padding: 8px 20px;
  border-radius: 20px;
  cursor: pointer;
  font-size: 0.9em;
  margin-top: 15px;
  transition: transform 0.2s, box-shadow 0.2s;
}
.news-toggle:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
}
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-10px); }
  to { opacity: 1; transform: translateY(0); }
}
@keyframes pulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(245, 87, 108, 0.4); }
  50% { box-shadow: 0 0 0 8px rgba(245, 87, 108, 0); }
}
</style>

# News

<div class="news-container">
  <div class="news-item">
    <span class="news-badge new">Dec 2025</span>
    <span class="news-content">I joined the <a href="http://yuanjiacan.com/">Climate Impact Team</a> as a postdoctoral researcher in Fudan University.</span>
  </div>
  <div class="news-item">
    <span class="news-badge">Jun 2025</span>
    <span class="news-content">I received the President Award from Chinese Academy Sciences.</span>
  </div>
  <div class="news-item">
    <span class="news-badge">Jun 2025</span>
    <span class="news-content">My doctoral dissertation received the Outstanding Doctoral Dissertation Award in USTC (<a href="https://gradschool.ustc.edu.cn/static/upload/article/file/1757589656275/1757589656275-801943.pdf">link</a>)</span>
  </div>
  <!-- 如需添加更多条目，复制下面的模板并添加 class="news-hidden" -->
  <!--
  <div class="news-item news-hidden">
    <span class="news-badge">Mon YYYY</span>
    <span class="news-content">Your news content here.</span>
  </div>
  -->
</div>

<button class="news-toggle" id="newsToggle" style="display:none;" onclick="toggleNews()">Show More</button>

<script>
(function() {
  const maxVisible = 5;
  const items = document.querySelectorAll('.news-item');
  const toggleBtn = document.getElementById('newsToggle');
  let expanded = false;
  
  // 初始化：隐藏超过5条的新闻
  if (items.length > maxVisible) {
    items.forEach((item, index) => {
      if (index >= maxVisible) {
        item.classList.add('news-hidden');
      }
    });
    toggleBtn.style.display = 'inline-block';
    toggleBtn.textContent = `Show More (${items.length - maxVisible} hidden)`;
  }
  
  window.toggleNews = function() {
    expanded = !expanded;
    items.forEach((item, index) => {
      if (index >= maxVisible) {
        item.classList.toggle('news-hidden', !expanded);
      }
    });
    toggleBtn.textContent = expanded ? 'Show Less' : `Show More (${items.length - maxVisible} hidden)`;
  };
})();
</script>

<script type="text/javascript" id="mapmyvisitors" src="//mapmyvisitors.com/map.js?d=5NB7l-1kcgLGMqCgrOrR-ek2FJHURhFX0lYH5om7Zkc&cl=ffffff&w=a"></script>