---
layout: page
sitemap: false
permalink: /template/
title: My Template Title
# Page menu is optional
menu: template
# Hero is optional (only the title will appear)
hero: 
  # If no image is specified there is a basic gray color background
  image: /assets/img/bgimg-mobile.jpg
  # Dont go too crazy with the description...
  description:
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam arcu nunc, dignissim sed sapien non, aliquam tincidunt quam. Vivamus justo velit, tristique et orci in, commodo ornare nibh.
  buttons:
    - title: Test button 1
      url: /template/test1/
      highlight: true
    - title: Test button 2
      url: /template/test2/
# Downloads is optional (it will make the page wider)
downloads:
  - title: Template document
    url: /downloads/template-document.pdf
  - title: Template images
    url: /downloads/template-images.svg
    filename: download-with-forced-filename.svg
# Scrollspy is optional (it will make the page wider)
scrollspy:
  - id: ungrouped-title-1
    name: Ungrouped Title 1
  - id: ungrouped-title-2
    name: Ungrouped Title 2
  - name: Menu Group 1
    subspies:
    - id: title-1
      name: Title 1
    - id: subtitle-1-1
      name: Subtitle 1 1
    - id: subtitle-1-2
      name: Subtitle 1 2
    - id: title-2
      name: Title 2
  - name: Menu Group 2
    subspies:
    - id: title-3
      name: Title 3
    - id: title-4
      name: Title 4

# Markdown reference: https://kramdown.gettalong.org/quickref.html
# Bootstrap reference: https://getbootstrap.com/docs/4.0/
---

# Ungrouped Title 1

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam arcu nunc, dignissim sed sapien non, aliquam tincidunt quam. Vivamus justo velit, tristique et orci in, commodo ornare nibh. Vivamus malesuada turpis magna, ac posuere urna accumsan ornare. Duis tincidunt, neque ac efficitur pulvinar, eros risus lacinia ante, vitae lacinia lorem leo at mi. *Pellentesque* vel lorem malesuada lectus convallis ornare. In iaculis tellus id justo eleifend cursus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nulla semper, turpis et hendrerit hendrerit, eros erat imperdiet augue, eu condimentum dui orci nec sem. Nam tincidunt nulla enim, in faucibus augue lobortis sed. In auctor magna id velit lobortis fermentum. Sed urna augue, vulputate vitae egestas ut, ornare eget neque. Donec in mattis ligula. Nulla et varius turpis. Maecenas efficitur ex nec suscipit molestie.

An image:

![example image](/assets/img/bgimg-mobile.jpg)

Nunc sit amet lectus elit. Ut vitae tellus faucibus, gravida eros id, volutpat velit. Duis pretium tellus a cursus hendrerit. Phasellus tincidunt odio ex, vitae cursus sapien facilisis mollis. Suspendisse potenti. Aenean ullamcorper non enim a aliquet. Maecenas accumsan dapibus gravida.

And a figure (recommended for caption :D):

<figure class="figure">
  <img src="/assets/img/bgimg-mobile.jpg" class="figure-img img-fluid rounded" alt="A generic square placeholder image with rounded corners in a figure.">
  <figcaption class="figure-caption text-right">A caption for the above image.</figcaption>
</figure>

# Ungrouped Title 2

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam arcu nunc, dignissim sed sapien non, aliquam tincidunt quam. Vivamus justo velit, tristique et orci in, commodo ornare nibh. Vivamus malesuada turpis magna, ac posuere urna accumsan ornare. Duis tincidunt, neque ac efficitur pulvinar, eros risus lacinia ante, vitae lacinia lorem leo at mi. Pellentesque vel lorem malesuada lectus convallis ornare. In iaculis tellus id justo eleifend cursus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nulla semper, turpis et hendrerit hendrerit, eros erat imperdiet augue, eu condimentum dui orci nec sem. Nam tincidunt nulla enim, in faucibus augue lobortis sed. In auctor magna id velit lobortis fermentum. Sed urna augue, vulputate vitae egestas ut, ornare eget neque. Donec in mattis ligula. Nulla et varius turpis. Maecenas efficitur ex nec suscipit molestie.

Now I'm writting some code: `import numpy as np`

~~~ python
def test(a, b):
  return a + b
end
~~~

# Title 1

Nunc sit amet lectus elit. Ut vitae tellus faucibus, gravida eros id, volutpat velit. Duis pretium tellus a cursus hendrerit. Phasellus tincidunt odio ex, vitae cursus sapien facilisis mollis. Suspendisse potenti. Aenean ullamcorper non enim a aliquet. Maecenas accumsan dapibus gravida.+

I need a separator 

---

yeeaah

---


## Subtitle 1 1

Vestibulum eleifend ex ut massa congue, laoreet aliquam metus finibus. Curabitur congue eros id eleifend iaculis. Aenean hendrerit metus nibh, vitae efficitur arcu hendrerit sit amet. Aenean id sapien eros. Morbi quis vulputate dolor, eget gravida ipsum. Vestibulum rutrum nisl a orci ultrices lobortis quis efficitur ligula. Nam placerat justo a nibh aliquam, quis cursus turpis sodales. Vivamus vestibulum lectus et blandit fringilla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Pellentesque ultricies efficitur tortor, quis finibus quam vehicula ut. Donec at quam velit. Praesent luctus neque interdum, ultrices arcu facilisis, feugiat mi. Quisque vitae magna commodo, tempor lacus id, tristique dolor. Quisque ut orci vitae libero viverra cursus. Nam eros elit, rutrum sit amet justo eu, commodo mollis erat. Donec quam sapien, consectetur ut tristique in, porttitor eu urna.

And a quote ( ... need html for getting it cool :(((( ):

<blockquote class="blockquote">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>


Suspendisse ex dui, sagittis vitae pulvinar ut, aliquet non nisi. Donec faucibus arcu felis, imperdiet pellentesque quam porttitor sed. Curabitur pellentesque orci eu interdum rhoncus. Vestibulum pulvinar bibendum efficitur. Morbi cursus quam a nulla blandit faucibus. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras porttitor diam at arcu faucibus, in semper urna sagittis. Aenean arcu eros, mollis nec mi ut, auctor malesuada velit. Curabitur aliquam convallis laoreet. Nullam justo dolor, consectetur ut ullamcorper semper, dictum id tellus.

## Subtitle 1 2

Suspendisse ex dui, sagittis vitae pulvinar ut, aliquet non nisi. Donec faucibus arcu felis, imperdiet pellentesque quam porttitor sed. Curabitur pellentesque orci eu interdum rhoncus. Vestibulum pulvinar bibendum efficitur. Morbi cursus quam a nulla blandit faucibus. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras porttitor diam at arcu faucibus, in semper urna sagittis. Aenean arcu eros, mollis nec mi ut, auctor malesuada velit. Curabitur aliquam convallis laoreet. Nullam justo dolor, consectetur ut ullamcorper semper, dictum id tellus.

This is cool for listing terms:

term
: definition
: another definition

another term
and another term
: and a definition for the term

# Title 2

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam arcu nunc, dignissim sed sapien non, aliquam tincidunt quam. Vivamus justo velit, tristique et orci in, commodo ornare nibh. Vivamus malesuada turpis magna, ac posuere urna accumsan ornare. Duis tincidunt, neque ac efficitur pulvinar, eros risus lacinia ante, vitae lacinia lorem leo at mi. Pellentesque vel lorem malesuada lectus convallis ornare. In iaculis tellus id justo eleifend cursus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nulla semper, turpis et hendrerit hendrerit, eros erat imperdiet augue, eu condimentum dui orci nec sem. Nam tincidunt nulla enim, in faucibus augue lobortis sed. In auctor magna id velit lobortis fermentum. Sed urna augue, vulputate vitae egestas ut, ornare eget neque. Donec in mattis ligula. Nulla et varius turpis. Maecenas efficitur ex nec suscipit molestie.

Tables!! yaaay!

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{:class="table"}

Vestibulum eleifend ex ut massa congue, laoreet aliquam metus finibus. Curabitur congue eros id eleifend iaculis. Aenean hendrerit metus nibh, vitae efficitur arcu hendrerit sit amet. Aenean id sapien eros. Morbi quis vulputate dolor, eget gravida ipsum. Vestibulum rutrum nisl a orci ultrices lobortis quis efficitur ligula. Nam placerat justo a nibh aliquam, quis cursus turpis sodales. Vivamus vestibulum lectus et blandit fringilla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Pellentesque ultricies efficitur tortor, quis finibus quam vehicula ut. Donec at quam velit. Praesent luctus neque interdum, ultrices arcu facilisis, feugiat mi. Quisque vitae magna commodo, tempor lacus id, tristique dolor. Quisque ut orci vitae libero viverra cursus. Nam eros elit, rutrum sit amet justo eu, commodo mollis erat. Donec quam sapien, consectetur ut tristique in, porttitor eu urna.

And maybe a cool reference[^1]. Or maybe 2[^2]. And for the same one[^1].

Suspendisse ex dui, sagittis vitae pulvinar ut, aliquet non nisi. Donec faucibus arcu felis, imperdiet pellentesque quam porttitor sed. Curabitur pellentesque orci eu interdum rhoncus. Vestibulum pulvinar bibendum efficitur. Morbi cursus quam a nulla blandit faucibus. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras porttitor diam at arcu faucibus, in semper urna sagittis. Aenean arcu eros, mollis nec mi ut, auctor malesuada velit. Curabitur aliquam convallis laoreet. Nullam justo dolor, consectetur ut ullamcorper semper, dictum id tellus.


# Title 3

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam arcu nunc, dignissim sed sapien non, aliquam tincidunt quam. Vivamus justo velit, tristique et orci in, commodo ornare nibh. Vivamus malesuada turpis magna, ac posuere urna accumsan ornare. Duis tincidunt, neque ac efficitur pulvinar, eros risus lacinia ante, vitae lacinia lorem leo at mi. Pellentesque vel lorem malesuada lectus convallis ornare. In iaculis tellus id justo eleifend cursus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Nulla semper, turpis et hendrerit hendrerit, eros erat imperdiet augue, eu condimentum dui orci nec sem. Nam tincidunt nulla enim, in faucibus augue lobortis sed. In auctor magna id velit lobortis fermentum. Sed urna augue, vulputate vitae egestas ut, ornare eget neque. Donec in mattis ligula. Nulla et varius turpis. Maecenas efficitur ex nec suscipit molestie.

# Title 4

Suspendisse ex dui, sagittis vitae pulvinar ut, aliquet non nisi. Donec faucibus arcu felis, imperdiet pellentesque quam porttitor sed. Curabitur pellentesque orci eu interdum rhoncus. Vestibulum pulvinar bibendum efficitur. Morbi cursus quam a nulla blandit faucibus. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras porttitor diam at arcu faucibus, in semper urna sagittis. Aenean arcu eros, mollis nec mi ut, auctor malesuada velit. Curabitur aliquam convallis laoreet. Nullam justo dolor, consectetur ut ullamcorper semper, dictum id tellus.

[esto es un link](https://ingelectus.com)

Vestibulum eleifend ex ut massa congue, laoreet aliquam metus finibus. Curabitur congue eros id eleifend iaculis. Aenean hendrerit metus nibh, vitae efficitur arcu hendrerit sit amet. Aenean id sapien eros. Morbi quis vulputate dolor, eget gravida ipsum. Vestibulum rutrum nisl a orci ultrices lobortis quis efficitur ligula. Nam placerat justo a nibh aliquam, quis cursus turpis sodales. Vivamus vestibulum lectus et blandit fringilla. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Pellentesque ultricies efficitur tortor, quis finibus quam vehicula ut. Donec at quam velit. Praesent luctus neque interdum, ultrices arcu facilisis, feugiat mi. Quisque vitae magna commodo, tempor lacus id, tristique dolor. Quisque ut orci vitae libero viverra cursus. Nam eros elit, rutrum sit amet justo eu, commodo mollis erat. Donec quam sapien, consectetur ut tristique in, porttitor eu urna.

* Lists!!!
  * and sublists!!
  * :)
* yaaaay
* more items!!

Suspendisse ex dui, sagittis vitae pulvinar ut, aliquet non nisi. Donec faucibus arcu felis, imperdiet pellentesque quam porttitor sed. Curabitur pellentesque orci eu interdum rhoncus. Vestibulum pulvinar bibendum efficitur. Morbi cursus quam a nulla blandit faucibus. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras porttitor diam at arcu faucibus, in semper urna sagittis. Aenean arcu eros, mollis nec mi ut, auctor malesuada velit. Curabitur aliquam convallis laoreet. Nullam justo dolor, consectetur ut ullamcorper semper, dictum id tellus.

1. Numbered lists too
2. Im number 2
3. And Im 3!

Suspendisse ex dui, sagittis vitae pulvinar ut, aliquet non nisi. Donec faucibus arcu felis, imperdiet pellentesque quam porttitor sed. Curabitur pellentesque orci eu interdum rhoncus. Vestibulum pulvinar bibendum efficitur. Morbi cursus quam a nulla blandit faucibus. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras porttitor diam at arcu faucibus, in semper urna sagittis. Aenean arcu eros, mollis nec mi ut, auctor malesuada velit. Curabitur aliquam convallis laoreet. Nullam justo dolor, consectetur ut ullamcorper semper, dictum id tellus.

## References

[^1]: Reference 1!!!!
[^2]:
    Reference 2 is a bit longer so i'm writting it down here :)