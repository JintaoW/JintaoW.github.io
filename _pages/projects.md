---
layout: page
title: 项目成果
permalink: /projects/
description: 主持与参与的科研项目、教学改革项目，以及专利授权与软件著作权。
nav: true
nav_order: 3
display_categories: [科研项目, 教学项目, 专利授权, 软件著作权]
---

<!-- pages/projects.md ：按类别以纯列表形式列出，不做卡片。 -->
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
