# Surveys-Flask_MySQL_CRUD_Practice-CodingDojo
### Python - FLask - MySQL - CRUD - validations
### install packages
* ``` pipenv install PyMySQL flask ```
* ``` pipenv shell ```
* ``` python server.py ```
### validation code using flash ``` survey_model.py ``` 
```{PYTHON}
 @staticmethod
    def validate_survey(survey):
        is_valid = True
        if len(survey['name']) < 3:
            is_valid = False
            flash("el nombre debe tener al menos 3 caracteres")
        if len(survey['location']) == 0:
            is_valid = False
            flash("debe elejir una locacion")
        if len(survey['language']) == 0:
            is_valid = False
            flash("debe elegir un lenguaje")
        if len(survey['comment']) < 5:
            is_valid = False
            flash("debe escribir un comentario al menos 5 palabras")
        return is_valid
 ```
 ### Template ``` index-html ``` 
 ```{html} 
     <div>
                {% with messages = get_flashed_messages() %}     
                {% if messages %}                            
                    {% for message in messages %}            
                        <p class="text-danger">{{message}}</p>                   
                    {% endfor %}
                {% endif %}
                {% endwith %}
    </div>
 ``` 
