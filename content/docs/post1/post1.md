+++
title = 'Test'
date = 2024-11-16T07:54:35-05:00
draft = true
tags = ["hugo", "github actions", "github pages"]
categories = ["math","programming","art","AI"]
+++

# some code 

## inline code 

Here is some `inline code` that you can use in a paragraph.

some other inline `< figure src="../image1.jpg" alt="Description of the image" caption="Your caption text here" class="align-center" >` code.

## bloc code 

```python
def something():
    return tmr
```

# this is a equation 

testing inline equations $a-3$ | wave equations $i\hbar \frac{\partial}{\partial t} \Psi = \hat{H}\Psi$, now math block:

$$
i\hbar \frac{\partial}{\partial t} \Psi = \hat{H}\Psi
$$

**testing max lenght**: this is some randon words randon words randon words randon words randon words randon words randon wordsrandon wordsrandon wordsrandon words randon words 
this is a block equations 

testing math bloc equations

$$
L(G, D) = \int_x \bigg( p_{r}(x) \log(D(x)) + p_g (x) \log(1 - D(x)) \bigg) dx
$$


if you are using something using alignment, do not forget to use `\\\` to break lines
$$
\begin{aligned}
 AR(p): Y_i &= c + \epsilon_i + \phi_i Y_{i-1} \dots \\\
 Y_{i} &= c + \phi_i Y_{i-1} \dots
\end{aligned}
$$

Example of how **hyperlinks** look like:

believe ([Huszar, 2015](https://stackoverflow.com/questions/27081054/r-markdown-math-equation-alignment)) that one reason behind

**items** example 
- item1
- item 2
- item 3

## image with caption 
what worked at the end: do not forget to enclose this code with `{{}}`
```html
< figure src="../image1.jpg" alt="Description of the image" caption="Your caption text here" class="align-center" >
```
### simple 

{{< figure src="../image1.jpg" alt="Description of the image" caption="You Your bold and larger caption text here Your bold and larger caption text here Your bold and larger caption text here Your bold and larger caption text here Your bold and larger caption text here Your bold and larger caption textr caption text here" class="align-center" >}}

## include soundcloud

how to do it?
- go to the song
- push the `share` buttom
- choose `embed` option

<iframe width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/1876617552&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe>
<div style="font-size: 10px; color: #cccccc; line-break: anywhere; word-break: normal; overflow: hidden; white-space: nowrap; text-overflow: ellipsis; font-family: Interstate, Lucida Grande, Lucida Sans Unicode, Lucida Sans, Garuda, Verdana, Tahoma, sans-serif; font-weight: 100;">
  <a href="https://soundcloud.com/alanwalker" title="Alan Walker" target="_blank" style="color: #cccccc; text-decoration: none;">Alan Walker</a> · 
  <a href="https://soundcloud.com/alanwalker/alan-walker-barcelona-carstn-remix" title="Alan Walker - Barcelona (CARSTN Remix)" target="_blank" style="color: #cccccc; text-decoration: none;">Alan Walker - Barcelona (CARSTN Remix)</a>
</div>

## template citation 

# Citation

Cited as:
> Takagui-Perez, R. Kenyi. `insert_blog_name`.. Kenyi'Log.  
> `link_of_the_blog`

Or


```
@article{something,
  title   = "insert blog name.",
  author  = "Takagui-Perez, R. Kenyi",
  journal = "taogenna.github.io",
  year    = "insert year",
  month   = "insert abr of month",
  url     = "insert complete link"
}
```