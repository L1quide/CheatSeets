[❰❰❰](https://github.com/L1quide/CheatSeets/blob/master/Django_main.md)  [HOME](https://github.com/L1quide/CheatSeets/blob/master/README.md)

#### ✓ URL Django

▪ Как получить прямую ссылку на объект?

    # urls.py 
    ...
    path('contact/', views.contact, name='contact'),
    ...
    
    # шаблон.html   
    <a href="{% url 'contact' %}">contact</a>
    

▪ Как получить уникальную ссылку на объект?

    # models.py
    def get_absolute_url(self):
        return reverse('detail', args=[str(self.slug)])
      
    # views.py
    def detail(request, slug):
        content = Crud.objects.get(slug=slug)
        return render(request, 'detail.html', {'content': content})
        
    # шаблон.html   
    {{ content.description }} 
    
    # urls.py 
    ...
    path('<slug:slug>/', views.detail, name='detail'),
    ...  

[get_absolute_url()](https://django.fun/docs/django/ru/3.0/ref/models/instances/#get-absolute-url)

[reverse()](https://django.fun/docs/django/ru/3.0/ref/urlresolvers/#django.urls.reverse)
