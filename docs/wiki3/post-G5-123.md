---
share: true
title: post G5 123
category: wiki3
description: лучшее описание
hide:
  - footer
image: _Files_/Pasted%20image%2020221224070649.png
---

# tip

``` py title="bubble_sort.py"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```


``` yaml
theme:
  features:
    - content.code.annotate # (1)
```

1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.




# top1

[post 4](../wiki4/second-my-post2.md)


# top2

![post 4](../wiki4/second-my-post2.md#soft1)




# Howto Collapsible Sections in GitHub Markdown




![`Scrum`](../wiki4/скрам-на-проектах.md#Scrum)
