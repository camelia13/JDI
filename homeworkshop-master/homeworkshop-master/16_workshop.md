16_workshop

## 01_문제

- models.py

```python
from django.db import models

# Create your models here.
class Student(models.Model):
    name = models.CharField(max_length=15)
    email = models.CharField(max_length=100)
    birthday = models.DateField() #날짜를 선택할 수 있음
    age = models.IntegerField()

    def __str__(self):
        return f'{self.id} - 이름: {self.name}, 이메일: {self.email}, 생일: {self.birthday}, 나이: {self.age}'
```

- 0001_initial.py

```python
# Generated by Django 2.2.4 on 2019-08-09 00:15

from django.db import migrations, models


class Migration(migrations.Migration):

    initial = True

    dependencies = [
    ]

    operations = [
        migrations.CreateModel(
            name='Student',
            fields=[
                ('id', models.AutoField(auto_created=True, primary_key=True, serialize=False, verbose_name='ID')),
                ('name', models.CharField(max_length=15)),
                ('email', models.CharField(max_length=100)),
                ('birthday', models.DateField()),
                ('age', models.IntegerField()),
            ],
        ),
    ]

```

- admin.py

```python
from django.contrib import admin
from .models import Student
# Register your models here.

class StudentAdmin(admin.ModelAdmin):
    list_display = ('id', 'name', 'email', 'birthday', 'age')

admin.site.register(Student, StudentAdmin)

```

