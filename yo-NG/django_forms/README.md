# Àwọn fọ́ọ̀mù Django

Ohun tó kẹ́yìn tí a fẹ́ ṣe lórí ààyè ayélujára wa ni láti ṣẹ̀dá ọ̀nà tó dára kan láti ṣàfikún àti ṣàtúnṣe àwọn àròkọ blog. `admin` ti Django dára, ṣùgbọ́n ó ṣòro láti ṣé bí o ṣe fẹ́ àti láti mú rẹwà. Pẹ̀lú `forms`, a máa ní gbogbo agbára lórí atọ́kùn wa – a lè fẹ́rẹ̀ẹ́ ṣe ohunkóhun tí a lè wòye sí!

Ohun tó dára nípa àwọn fọ́ọ̀mù Django ni pé a lè ṣàlàyé ìkan láti ìbẹ̀rẹ̀ tàbí ṣẹ̀dá `ModelForm` kan èyí tí yíò tọ́jú èsì fọ́ọ̀mù náà sínú àwòṣe náà.

Èyí jẹ́ ohun tí a fẹ́ ṣe gan-an: a ó ṣẹ̀dá fọ́ọ̀mù kan fún àwòṣe `Post` wa.

Gẹ́gẹ́ bí gbogbo apá tó ṣe pàtàkì nínú Django, àwọn fọ́ọ̀mù ní fáìlì tiwọn: `forms.py`.

A nílò láti ṣẹ̀dá fáìlì kan pẹ̀lú orúkọ yìí nínú àkójọpọ̀ fáìlì `blog` náà.

    blog
       └── forms.py
    

O dáa, jẹ́ ká ṣí i nínú olóòtú kóòdù náà kí a sì tẹ kóòdù tó tẹ̀le yìí:

{% filename %}blog/forms.py{% endfilename %}

```python
from django import forms

from .models import Post

class PostForm(forms.ModelForm):

    class Meta:
        model = Post
        fields = ('title', 'text',)
```

A nílò láti ṣàgbéwọlé àwọn fọ́ọ̀mù Django lákọ̀ọ́kọ́ (`from django import forms`) àti àwòṣe `Post` wa (`from .models import Post`).

`PostForm`, bí o ṣe lérò, jẹ́ orúkọ fọ́ọ̀mù wa. We need to tell Django that this form is a `ModelForm` (so Django will do some magic for us) – `forms.ModelForm` is responsible for that.

Lẹ́yìn náà, a ní `class Meta`, níbi tí a ti máa sọ àwòṣe tó yẹ kí Django lò láti ṣẹ̀dá fọ́ọ̀mù yìí (`model = Post`).

Ní ìparí, a lè sọ (àwọn) ààyè tó yẹ kó wà nínú fọ́ọ̀mù wa. In this scenario we want only `title` and `text` to be exposed – `author` should be the person who is currently logged in (you!) and `created_date` should be automatically set when we create a post (i.e. in the code), right?

And that's it! All we need to do now is use the form in a *view* and display it in a template.

So once again we will create a link to the page, a URL, a view and a template.

## Link to a page with the form

It's time to open `blog/templates/blog/base.html` in the code editor. We will add a link in `div` named `page-header`:

{% filename %}blog/templates/blog/base.html{% endfilename %}

```html
<a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
```

Note that we want to call our new view `post_new`. The class `"glyphicon glyphicon-plus"` is provided by the bootstrap theme we are using, and will display a plus sign for us.

After adding the line, your HTML file should now look like this:

{% filename %}blog/templates/blog/base.html{% endfilename %}

```html
{% load static %}
<html>
    <head>
        <title>Django Girls blog</title>
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
        <link href='//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext' rel='stylesheet' type='text/css'>
        <link rel="stylesheet" href="{% static 'css/blog.css' %}">
    </head>
    <body>
        <div class="page-header">
            <a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
            <h1><a href="/">Django Girls Blog</a></h1>
        </div>
        <div class="content container">
            <div class="row">
                <div class="col-md-8">
                    {% block content %}
                    {% endblock %}
                </div>
            </div>
        </div>
    </body>
</html>
```

Lẹ́yìn títọ́jú àti ṣíṣe ìmúdójúìwọ̀n ojú-ìwé http://127.0.0.1:8000 náà, ìwọ yíò rí àṣìṣe `NoReverseMatch` tí o mọ́ nípa. Ṣé bó ṣe rí nìyẹn? O dáa!

## URL

A ṣí `blog/urls.py` nínú olóòtú kóòdù náà àti ṣàfikún ìlà kan:

{% filename %}blog/urls.py{% endfilename %}

```python
path('post/new/', views.post_new, name='post_new'),
```

Àti pé kóòdù ìparí náà yíò rí báyìí:

{% filename %}blog/urls.py{% endfilename %}

```python
from django.urls import path 
from . import views

urlpatterns = [
    path('', views.post_list, name='post_list'),
    path('post/<int:pk>/', views.post_detail, name='post_detail'),
    path('post/new/', views.post_new, name='post_new'),
]
```

Lẹ́yìn ṣíṣe ìmúdójúìwọ̀n ààyè náà, a rí `AttributeError` kan, nítorí pé a kò ní view `post_new` náà ní ṣíṣe. Jẹ́ ká ṣàfikún rẹ̀ ní báyìí.

## view post_new

Àkókò láti ṣí fáìlì `blog/views.py` nínú olóòtú kóòdù náà àti ṣàfikún àwọn ìlà tó tẹ̀le yìí pẹ̀lú àwọn ìlà `from` yòókù náà:

{% filename %}blog/views.py{% endfilename %}

```python
from .forms import PostForm
```

Lẹ́yìn náà *view* wa:

{% filename %}blog/views.py{% endfilename %}

```python
def post_new(request):
    form = PostForm()
    return render(request, 'blog/post_edit.html', {'form': form})
```

Láti ṣẹ̀dá fọ́ọ̀mù `Post` tuntun kan, a nílò láti pe `PostForm()` kí a sì darí rẹ̀ sí àwòṣe (template) náà. A ó padà sí *view* yìí, ṣùgbọ́n ní báyìí, jẹ́ ká tètè ṣẹ̀dá àwòṣe (template) kan fún fọ́ọ̀mù náà.

## Àwòṣe (template)

A nílò láti ṣẹ̀dá fáìlì `post_edit.html` kan nínú àkójọpọ̀ fáìlì `blog/templates/blog` náà, kí a sì ṣí nínú olóòtú kóòdù náà. Láti mú kí fọ́ọ̀mù kan ṣiṣẹ́, a nílò àwọn nnkan bíi mélòó kan:

* A ní láti ṣàfihàn fọ́ọ̀mù náà. A lè ṣe ìyẹn pẹ̀lú (fún àpẹẹrẹ) {% raw %}`{{ form.as_p }}`{% endraw %}.
* Ìlà tó wà lókè yìí nílò láti gba wíwé pẹ̀lú àmì fọ́ọ̀mù HTML kan: `<form method="POST">...</form>`.
* A nílò bọ́tìnnì `Save` kan. A lè ṣe ìyẹn pẹ̀lú bọ́tìnnì HTML kan: `<button type="submit">Save</button>`.
* Ní ìparí, kété lẹ́yìn àmì `<form ...>` ṣíṣí náà, a nílò láti ṣàfikún {% raw %}`{% csrf_token %}`{% endraw %}. Èyí ṣe pàtàkì púpọ̀, nítorí pé yóò pèsè ààbò fún àwọn fọ́ọ̀mù rẹ! Tí o bá gbàgbé nípa apá yìí, Django yíò ṣàròyé nígbà tí o bá gbìyànjú láti tọ́jú fọ́ọ̀mù náà:

![Ojú-ìwé Forbidden CSRF](images/csrf2.png)

O dáa, jẹ́ ká wo bó ṣe yẹ kí HTML inú `post_edit.html` rí:

{% filename %}blog/templates/blog/post_edit.html{% endfilename %}

```html
{% extends 'blog/base.html' %}

{% block content %}
    <h2>New post</h2>
    <form method="POST" class="post-form">{% csrf_token %}
        {{ form.as_p }}
        <button type="submit" class="save btn btn-default">Save</button>
    </form>
{% endblock %}
```

Time to refresh! Yay! Your form is displayed!

![Fọ́ọ̀mù tuntun](images/new_form2.png)

But, wait a minute! When you type something in the `title` and `text` fields and try to save it, what will happen?

Nothing! We are once again on the same page and our text is gone… and no new post is added. So what went wrong?

The answer is: nothing. We need to do a little bit more work in our *view*.

## Saving the form

Open `blog/views.py` once again in the code editor. Currently all we have in the `post_new` view is the following:

{% filename %}blog/views.py{% endfilename %}

```python
def post_new(request):
    form = PostForm()
    return render(request, 'blog/post_edit.html', {'form': form})
```

When we submit the form, we are brought back to the same view, but this time we have some more data in `request`, more specifically in `request.POST` (the naming has nothing to do with a blog "post"; it's to do with the fact that we're "posting" data). Remember how in the HTML file, our `<form>` definition had the variable `method="POST"`? All the fields from the form are now in `request.POST`. You should not rename `POST` to anything else (the only other valid value for `method` is `GET`, but we have no time to explain what the difference is).

So in our *view* we have two separate situations to handle: first, when we access the page for the first time and we want a blank form, and second, when we go back to the *view* with all form data we just typed. So we need to add a condition (we will use `if` for that):

{% filename %}blog/views.py{% endfilename %}

```python
if request.method == "POST":
    [...]
else:
    form = PostForm()
```

It's time to fill in the dots `[...]`. If `method` is `POST` then we want to construct the `PostForm` with data from the form, right? We will do that as follows:

{% filename %}blog/views.py{% endfilename %}

```python
form = PostForm(request.POST)
```

The next thing is to check if the form is correct (all required fields are set and no incorrect values have been submitted). We do that with `form.is_valid()`.

We check if the form is valid and if so, we can save it!

{% filename %}blog/views.py{% endfilename %}

```python
if form.is_valid():
    post = form.save(commit=False)
    post.author = request.user
    post.published_date = timezone.now()
    post.save()
```

Basically, we have two things here: we save the form with `form.save` and we add an author (since there was no `author` field in the `PostForm` and this field is required). `commit=False` means that we don't want to save the `Post` model yet – we want to add the author first. Most of the time you will use `form.save()` without `commit=False`, but in this case, we need to supply it. `post.save()` will preserve changes (adding the author) and a new blog post is created!

Finally, it would be awesome if we could immediately go to the `post_detail` page for our newly created blog post, right? To do that we need one more import:

{% filename %}blog/views.py{% endfilename %}

```python
from django.shortcuts import redirect
```

Add it at the very beginning of your file. And now we can say, "go to the `post_detail` page for the newly created post":

{% filename %}blog/views.py{% endfilename %}

```python
return redirect('post_detail', pk=post.pk)
```

`post_detail` is the name of the view we want to go to. Remember that this *view* requires a `pk` variable? To pass it to the views, we use `pk=post.pk`, where `post` is the newly created blog post!

OK, we've talked a lot, but we probably want to see what the whole *view* looks like now, right?

{% filename %}blog/views.py{% endfilename %}

```python
def post_new(request):
    if request.method == "POST":
        form = PostForm(request.POST)
        if form.is_valid():
            post = form.save(commit=False)
            post.author = request.user
            post.published_date = timezone.now()
            post.save()
            return redirect('post_detail', pk=post.pk)
    else:
        form = PostForm()
    return render(request, 'blog/post_edit.html', {'form': form})
```

Let's see if it works. Go to the page http://127.0.0.1:8000/post/new/, add a `title` and `text`, save it… and voilà! The new blog post is added and we are redirected to the `post_detail` page!

You might have noticed that we are setting the publish date before saving the post. Later on, we will introduce a *publish button* in **Django Girls Tutorial: Extensions**.

That is awesome!

> As we have recently used the Django admin interface, the system currently thinks we are still logged in. There are a few situations that could lead to us being logged out (closing the browser, restarting the DB, etc.). If, when creating a post, you find that you are getting errors referring to the lack of a logged-in user, head to the admin page http://127.0.0.1:8000/admin and log in again. This will fix the issue temporarily. There is a permanent fix awaiting you in the **Homework: add security to your website!** chapter after the main tutorial.

![Àṣìṣe wíwọlé](images/post_create_error.png)

## Form validation

Now, we will show you how cool Django forms are. A blog post needs to have `title` and `text` fields. In our `Post` model we did not say that these fields (as opposed to `published_date`) are not required, so Django, by default, expects them to be set.

Try to save the form without `title` and `text`. Guess what will happen!

![Fífìdí fọ́ọ̀mù múlẹ̀](images/form_validation2.png)

Django is taking care to validate that all the fields in our form are correct. Isn't it awesome?

## Fọ́ọ̀mù àtúnṣe

Ní báyìí, a mọ bí a ṣe lè ṣàfikún fọ́ọ̀mù tuntun kan. Ṣùgbọ́n tí a bá fẹ́ ṣàtúnṣe ìkan tó ti wà tẹ́lẹ̀ ńkọ́? Èyí kò fi bẹ́ẹ̀ yàtọ̀ sí ohun tí a ṣẹ̀ṣẹ̀ ṣetán. Jẹ́ ká ṣẹ̀dá àwọn nnkan tó ṣe pàtàkì ní kíákíá. (Tí nnkan kan kò bá yé ọ, ó yẹ kí o béèrè lọ́wọ́ olùkọ́ rẹ tàbí kí o wo àwọn àkòrí tó ṣáájú náà, nítorí pé a ti ṣàlàyé gbogbo àwọn ìgbésẹ̀ wọ̀nyí tẹ́lẹ̀.)

Ṣí `blog/templates/blog/post_detail.html` nínú olóòtú kóòdù náà kí o sì ṣàfikún ìlà yìí

{% filename %}blog/templates/blog/post_detail.html{% endfilename %}

```html
<a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
```

kí àwòṣe (template) náà lè rí báyìí:

{% filename %}blog/templates/blog/post_detail.html{% endfilename %}

```html
{% extends 'blog/base.html' %}

{% block content %}
    <div class="post">
        {% if post.published_date %}
            <div class="date">
                {{ post.published_date }}
            </div>
        {% endif %}
        <a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
        <h2>{{ post.title }}</h2>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endblock %}
```

Ṣí `blog/urls.py` nínú olóòtú kóòdù náà, kí o sì ṣàfikún ìlà yìí:

{% filename %}blog/urls.py{% endfilename %}

```python
    path('post/<int:pk>/edit/', views.post_edit, name='post_edit'),
```

A ó tún lo àwòṣe (template) `blog/templates/blog/post_edit.html` náà, nítorí náà ohun tí a pàdánù kẹ́yìn ni *view* kan.

Jẹ́ ká ṣí `blog/views.py` nínú olóòtú kóòdù náà kí a sì ṣàfikún èyí ní ìgbẹ̀yìn fáìlì náà:

{% filename %}blog/views.py{% endfilename %}

```python
def post_edit(request, pk):
    post = get_object_or_404(Post, pk=pk)
    if request.method == "POST":
        form = PostForm(request.POST, instance=post)
        if form.is_valid():
            post = form.save(commit=False)
            post.author = request.user
            post.published_date = timezone.now()
            post.save()
            return redirect('post_detail', pk=post.pk)
    else:
        form = PostForm(instance=post)
    return render(request, 'blog/post_edit.html', {'form': form})
```

Èyí fẹ́rẹ̀ẹ́ rí bákannáà pẹ̀lú view `post_new` wa, àbí bẹ́ẹ̀ kọ? Ṣùgbọ́n kìí ṣe pátápátá. Lákọ̀ọ́kọ́ ná, a darí àfikún parameter `pk` kan láti urls. Lẹ́yìn náà, a gba àwòṣe `Post` tí a fẹ́ ṣàtúnṣe pẹ̀lú `get_object_or_404(Post, pk=pk)` àti pé, nígbà tí a bá ṣẹ̀dá fọ́ọ̀mù kan, a máa darí àròkọ yìí gẹ́gẹ́ bí `instance` kan, nígbà tí a bá tọ́jú fọ́ọ̀mù náà…

{% filename %}blog/views.py{% endfilename %}

```python
form = PostForm(request.POST, instance=post)
```

…àti nígbà tí a bá ṣẹ̀ṣẹ̀ ṣí fọ́ọ̀mù kan pẹ̀lú àròkọ yìí láti ṣàtúnṣe:

{% filename %}blog/views.py{% endfilename %}

```python
form = PostForm(instance=post)
```

Ó dáa, jẹ́ ká ṣàyẹ̀wò bóyá ó n ṣiṣẹ́! Jẹ́ ká lọ sí ojú-ìwé `post_detail` náà. Ó yẹ kí bọ́tìnnì àtúnṣe kan wà ní igun òkè lápá ọ̀tún náà:

![Bọ́tìnnì àtúnṣe](images/edit_button2.png)

Nígbà tí o bá tẹ̀ ẹ́, ìwọ yíò rí fọ́ọ̀mù náà pẹ̀lú àròkọ blog wa:

![Fọ́ọ̀mù àtúnṣe](images/edit_form2.png)

Má tijú láti ṣàyípadà àkọlé náà tàbí ọ̀rọ̀ náà kí o sì tọ́jú àwọn ìyípadà náà!

Kú oríire! Ètò rẹ túbọ̀ ń péye síi!

Tí o bá nílò àlàyé si nípa àwọn fọ́ọ̀mù Django, ó yẹ kí o ka àkọsílẹ̀ àlàyé náà: https://docs.djangoproject.com/en/2.0/topics/forms/

## Ààbò

Ṣíṣẹ̀dá àwọn àròkọ tuntun nípasẹ̀ títẹ atọ́ka kan dára púpọ̀! Ṣùgbọ́n ní báyìí, ẹnikẹ́ni tó bá ṣabẹ̀wò sí ààyè rẹ yóò lè ṣe àròkọ blog tuntun kan, àti pé kìí ṣe ohun tí o fẹ́. Jẹ́ ká ṣe é kí bọ́tìnnì náà máa hàn sí ìwọ ṣùgbọ́n kó pamọ́ fún ẹlòmíràn.

Ṣí `blog/templates/blog/base.html` nínú olóòtú kóòdù náà, wá `div` `page-header` wa àti àmì ajúwe ipò tí o fi síbẹ̀ ṣáájú. Ó yẹ kó rí báyìí:

{% filename %}blog/templates/blog/base.html{% endfilename %}

```html
<a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
```

A óò ṣàfikún àmì `{% if %}` mìíràn sí èyí, tí yíò mú kí atọ́ka náà hàn fún àwọn aṣàmúlò tó bá ti wọlé sínú alábòójútó náà nìkan. Ní báyìí, ìwọ nìkan ni! Ṣàyípadà àmì `<a>` náà láti rí báyìí:

{% filename %}blog/templates/blog/base.html{% endfilename %}

```html
{% if user.is_authenticated %}
    <a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
{% endif %}
```

`{% if %}` yìí yíò fi atọ́ka náà ránṣẹ́ sí aṣàwákiri náà tí aṣàmúlò tó bá ń béèrè ojú-ìwé náà bá ti wọlé nìkan. Èyí kò dáàbòbò ṣíṣẹ̀dá àwọn àròkọ tuntun pátápátá, ṣùgbọ́n ó jẹ́ ìgbésẹ̀ àkọ́kọ́ tó dára kan. A ó ṣàlàyé ààbò síwájú síi nínú àwọn ẹ̀kọ́ àfikún náà.

Rántí àwòrán aṣàmì àtúnṣe náà tí a ṣẹ̀ṣẹ̀ ṣàfikún sí ojú-ìwé detail wa? A tún fẹ́ ṣàfikún ìyípadà kannáà síbẹ̀, kí àwọn èèyàn mìíràn má lè ṣàtúnṣe àwọn àròkọ tó wà tẹ́lẹ̀.

Ṣí `blog/templates/blog/post_detail.html` nínú olóòtú kóòdù náà kí o sì wá ìlà yìí:

{% filename %}blog/templates/blog/post_detail.html{% endfilename %}

```html
<a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
```

Ṣàyípadà rẹ̀ sí èyí:

{% filename %}blog/templates/blog/post_detail.html{% endfilename %}

```html
{% if user.is_authenticated %}
     <a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
{% endif %}
```

Nítorí pé ó ṣeéṣe ko ti wọlé, tí o bá ṣe ìmúdójúìwọ̀n ojú-ìwé náà, ìwọ kò ní rí ìyàtọ̀ kankan. Ṣí ojú-ìwé náà nínú aṣàwákiri mìíràn kan tàbí fèrèsé kòlólúwa kan (tí a n pè ní "InPrivate" nínú Windows Edge), ìwọ yíò si rí pé atọ́ka náà kò fojú hàn, kódà àwòrán aṣàmì náà kò fojú hàn!

## Ó ṣì ku nnkan kan: àkókò láti ṣàgbékalẹ̀!

Jẹ́ ká wo bóyá gbogbo èyí yíò ṣiṣẹ́ lórí PythonAnywhere. Àkókò fún ṣíṣe àgbékalẹ̀ mìíràn!

* Lákọ̀ọ́kọ́, ṣàrídájú kóòdù tuntun rẹ, kí o sì tì í sí GitHub:

{% filename %}command-line{% endfilename %}

    $ git status
    $ git add --all .
    $ git status
    $ git commit -m "Added views to create/edit blog post inside the site."
    $ git push
    

* Lẹ́yìn náà, nínú [PythonAnywhere Bash console](https://www.pythonanywhere.com/consoles/) kan:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ cd ~/<your-pythonanywhere-domain>.pythonanywhere.com
    $ git pull
    [...]
    

(Rántí láti rọ́pò `<your-pythonanywhere-domain>` pẹ̀lú subdomain PythonAnywhere rẹ, láìsí àwọn àkámọ́ onígun náà.)

* Ní ìparí, lọ sí [ojú-ìwé "Ayélujára"](https://www.pythonanywhere.com/web_app_setup/) náà (lo bọ́tìnnì àkójọ àṣàyàn tó wà ní òkè lápá ọ̀tún console náà) kí o sì tẹ **Reload**. Ṣe ìmúdójúìwọ̀n blog https://subdomain.pythonanywhere.com rẹ láti rí àwọn ìyípadà náà.

A ó parí gbogbo rẹ̀ síbí! Kú oríire :)