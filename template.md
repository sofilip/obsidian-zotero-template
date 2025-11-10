---
documentclass: article
title: "{{title}}"
author: "{% for creator in creators %}{{creator.firstName}} {{creator.lastName}}{% if not loop.last %}, {% endif %}{% endfor %} ({{date | format('YYYY-MM-DD')}})"
date: \today
tags:
  - zotero
  - notes
colorlinks: true
csl: folder/ieee.csl
link-citations: true
---

{% for annotation in annotations -%}

{# 
   If a comment exists, use a Level 1 Heading (#) -> \section.
   The annotation details follow immediately as body text.
#}

{% if annotation.comment -%}

# {{annotation.comment}} (p. {{annotation.pageLabel}})

- **\colorbox{
  {%- if annotation.color == "#ff6666" -%}
    CustomRed
  {%- elif annotation.color == "#5fb236" -%}
    CustomGreen
  {%- elif annotation.color == "#2ea8e5" -%}
    CustomBlue
  {%- elif annotation.color == "#a28ae5" -%}
    CustomPurple
  {%- elif annotation.color == "#f19837" -%}
    CustomOrange
  {%- elif annotation.color == "#ffd400" -%}
    CustomYellow
  {%- elif annotation.color == "#e56eee" -%}
    CustomMagenta
  {%- elif annotation.color == "#aaaaaa" -%}
    CustomGray
  {%- else -%}
    black
  {%- endif -%}
}{\symbol{"200B}{{annotation.hashTags|replace("#", "")}}} (p. {{annotation.pageLabel}}):** {{annotation.annotatedText}}

{# 
   If NO comment exists, output only the quote details as simple paragraph text.
   This content will fall under the previous heading (or the main H1 above) 
   and will NOT be a new section/subsection.
#}
{%- else -%}

- **\colorbox{
  {%- if annotation.color == "#ff6666" -%}
    CustomRed
  {%- elif annotation.color == "#5fb236" -%}
    CustomGreen
  {%- elif annotation.color == "#2ea8e5" -%}
    CustomBlue
  {%- elif annotation.color == "#a28ae5" -%}
    CustomPurple
  {%- elif annotation.color == "#f19837" -%}
    CustomOrange
  {%- elif annotation.color == "#ffd400" -%}
    CustomYellow
  {%- elif annotation.color == "#e56eee" -%}
    CustomMagenta
  {%- elif annotation.color == "#aaaaaa" -%}
    CustomGray
  {%- else -%}
    black
  {%- endif -%}
}{\symbol{"200B}{{annotation.hashTags|replace("#", "")}}} (p. {{annotation.pageLabel}}):** {{annotation.annotatedText}}

{%- endif -%}

{%- if annotation.imageRelativePath %}

::: { #fig-yourlabel fig-pos="h!"} 
![ ](/folder/{{ annotation.imageRelativePath }}){width="50%"} 
:::

{%- endif %}

{% endfor %}


