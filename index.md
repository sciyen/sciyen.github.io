---
layout: default
---

<!-- Website Maintaining, please see [About](./about.md) -->

<h1>朱雁丞 Yen-Cheng Chu</h1>
<div class="intro-block">
    <div>
    我熱衷於結合科技與生活，製作 side project 或是 hacking 自己的生活。讓不會動的東西動起來是興趣，動得漂亮是浪漫。研究領域包含控制系統、非線性系統。偶爾嵌入式系統，設計電路板，或是寫網頁。
    </div>
    <div>
        <img src="../assets/me.png" class="img-circle">
    </div>
    <div>
        <ul>
            <li>Facebook: {% include icon-fb.html username=site.facebook_username url=site.facebook_url%}</li>
            {% if site.linkedin_username %}
            <li>LinkedIn: {% include icon-linkedin.html username=site.linkedin_username url=site.linkedin_url%}</li>
            {% endif %}
            {% if site.github_username %}
            <li>Github: {% include icon-github.html username="sciyen" %}</li>
            {% endif %}
            <li>Email: <a href="mailto:{{ site.email }}">{{ site.email }}</a></li>
        </ul>
    </div>
</div>