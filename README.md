# Ex02 Django ORM Web Application
## Date:15.04.2025
## Reg.no:212224220060

## AIM
To develop a Django application to store and retrieve data from Movies Database using Object Relational Mapping(ORM).

## ENTITY RELATIONSHIP DIAGRAM



## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for 10 books

## PROGRAM
```
admin.py

from django.contrib import admin
from .models import Movie

@admin.register(Movie)
class MovieAdmin(admin.ModelAdmin):
    list_display = ('title', 'genre', 'director', 'release_date', 'rating')
    list_filter = ('genre', 'release_date', 'rating')
    search_fields = ('title', 'director', 'genre')
    ordering = ('-release_date',)

models.py

from django.db import models

class Movie(models.Model):
    title = models.CharField(max_length=200)
    genre = models.CharField(max_length=100)
    director = models.CharField(max_length=100)
    release_date = models.DateField()
    duration_minutes = models.PositiveIntegerField()
    rating = models.DecimalField(max_digits=3, decimal_places=1)  # e.g., 8.5
    description = models.TextField(blank=True, null=True)

    def __str__(self):
        return f"{self.title} ({self.release_date.year})"

```



## OUTPUT
![alt text](<Screenshot 2025-04-15 142044.png>)

## RESULT
Thus the program for creating a database using ORM hass been executed successfully
