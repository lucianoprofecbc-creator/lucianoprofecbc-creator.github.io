---
layout: home
title: "🤔 Molestaciones matemáticas"
---

# 🤔 Molestaciones matemáticas

Bienvenidos.

Este es un blog sobre matemática, física matemática y las pequeñas ideas que uno va encontrando al estudiar.

## Entradas

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}