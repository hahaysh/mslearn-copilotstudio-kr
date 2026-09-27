---
title: 온라인 실습 가이드
permalink: index.html
layout: home
---

# Copilot Studio 실습

PL-7008 Microsoft Copilot Studio 한국어 실습 가이드는 다음과 같습니다.

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs-kr/'" %}
{% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }})
{% endfor %}
