---
title: "格式保留"
tags:
  - 介绍
  - 格式
  - 格式链接
#link: https://github.com
---

通知会显示说明附近内容的信息。通常用于引起对特定细节的注意。
使用通知时，{: .notice}可以在句子后面添加，以将分配.notice给<p></p>元素。


**服务变更:** 巴拉巴拉......
{: .notice}

**Primary Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. [Praesent libero](#). Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--primary}

**Info Notice:** Lorem ipsum dolor sit amet, [consectetur adipiscing elit](#). Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--info}

**Warning Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. [Integer nec odio](#). Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--warning}

**Danger Notice:** Lorem ipsum dolor sit amet, [consectetur adipiscing](#) elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--danger}

**Success Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at [nibh elementum](#) imperdiet.
{: .notice--success}

是否想在通知中包装几个段落或其他元素？使用Liquid捕获内容然后进行过滤markdownify是一个不错的方法。

```html
{% raw %}{% capture notice-2 %}
#### 新站点功能

* 您现在可以在博客页面上添加封面图像
* 草稿现在将在写入时自动保存
{% endcapture %}{% endraw %}

<div class="notice">{% raw %}{{ notice-2 | markdownify }}{% endraw %}</div>
```

{% capture notice-2 %}
#### 新站点功能

* 您现在可以在博客页面上添加封面图像
* 草稿现在将在写入时自动保存
{% endcapture %}

<div class="notice">
  {{ notice-2 | markdownify }}
</div>

或者，您可以跳过捕获并继续使用纯HTML。

```html
<div class="notice">
  <h4>Message</h4>
  <p>A basic message.</p>
</div>
```

<div class="notice">
  <h4>Message</h4>
  <p>A basic message.</p>
</div>
