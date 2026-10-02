---
layout: page
title: 专利与软著
permalink: /patents/
description: 发明专利授权与计算机软件著作权登记。
nav: true
nav_order: 3
display_categories: [专利授权, 软件著作权]
---

<!-- pages/patents.md ：专利与软著，按类别以纯列表形式列出，不做卡片。条目内容在 _projects/ 目录下（category 为“专利授权”或“软件著作权”）。 -->
<div class="projects">
  {% for category in page.display_categories %}
    <a id="{{ category }}" href=".#{{ category }}">
      <h2 class="category">{{ category }}</h2>
    </a>
    {% assign categorized_projects = site.projects | where: "category", category %}
    {% assign sorted_projects = categorized_projects | sort: "importance" %}
    <ul class="project-items">
      {% for project in sorted_projects %}
        <li>
          <span class="project-title">{{ project.title }}</span>
          <span class="project-desc">{{ project.description }}</span>
        </li>
      {% endfor %}
    </ul>
  {% endfor %}
</div>
