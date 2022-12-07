# Manage.py
- `python manage.py runserver`

# Three'step guide to making model changes:
- Change your models (in models.py)
- Run `python manage.py makemigrations` to create migrations for those changes
- Run `python manage.py migrate` to fapply those changes to the database.

# Admin site
Adding a Model to the admin panel
```python
from django.contrib import admin
from .models import Question

admin.site.register(Question)
```

# ORM
- For more information on model relations see [Accessing related objects](https://docs.djangoproject.com/en/4.1/ref/models/relations/).
- For more on how to use double underscores to perform fields lookups via the API, see [Field lookups](https://docs.djangoproject.com/en/4.1/topics/db/queries/#field-lookups-intro)
- For full details on the database API, see our [Database API Reference](https://docs.djangoproject.com/en/4.1/topics/db/queries/).

## Querying data with orm
- `Question.objects.all()`
- `Question.objects.filter(id=1)`
- `Question.objects.filter(question_text__startswith='What')`
- `Question.objects.get(pub_date__year=current_year)`
- `Question.objects.get(pk=1)` primary key lookup
- `q.choice_set.all()` related object set
- `Choice.objects.filter(question__pub_date__year=current_year)`

## Modifying data with orm
- `q.question_text = "How u doing?"; q.save()`
- `q.delete()`

# Examples of `django.utils.timezone`
- `timezone.now().year`
