---
title: 'La historia'
process:
    twig: true
content:
    items:
        'taxonomy@.category': [entrada]
    order:
        by: date
        dir: asc
    pagination: false
---

##La Historia

<ul>
    {% for p in page.find('/home').children if p != page %}
        <li>
            <div class="beginning-link">
                <a href="{{p.url}}/parte-1">{{ p.folder }}</a>
            </div>
            <div class="parts-link">
                <ul>
                    {% for child in p.children %}
                        <li>
                            <a href="{{child.url}}">{{child.header.part }}</a>
                        </li>
                    {% endfor %}
                </ul>
            </div>
        </li>
    {% endfor %}
</ul>