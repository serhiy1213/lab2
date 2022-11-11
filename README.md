Використання GitHub Actions

http://54.146.137.119/

Перше що я зробив це створив новий instance на aws

![image](https://user-images.githubusercontent.com/113981423/201423846-f2533b25-398e-4c8c-a0e0-6d7e60767127.png)

Потім створив нову гілку на репозиторіх. Так як ця гілка йде з main в неї є index.html

Зайшовши в preference, action, runner я натиснув на кнопку new self-host runner. Там я зміг зустріти команди, які потрібно було прописати у лінуксі

Залишилося прописати оці команди

![image](https://user-images.githubusercontent.com/113981423/201424322-356077cf-abba-4515-ad66-492afd88d191.png)

![image](https://user-images.githubusercontent.com/113981423/201424382-a0027128-200b-48ed-a5ed-482166951ee4.png)

Установив nginx на лінукс

Перейшови за /etc/nginx/sites-available, я видалив файл default і створив його заново

![image](https://user-images.githubusercontent.com/113981423/201425248-163e17e4-a3a4-458f-ab03-c7f3242d9366.png)


Перезапустив nginx ![image](https://user-images.githubusercontent.com/113981423/201424878-cad3a8f9-f3ef-4048-a004-fc03bde1ca9c.png)

Але для того щоб все спрацювало потрібно пройтися по директоріям які ведуть до нашого проекту і дати їм дозвіл ![image](https://user-images.githubusercontent.com/113981423/201425030-4b682e7d-1327-40ee-944a-05e0053aa964.png), ![image](https://user-images.githubusercontent.com/113981423/201425065-b054f838-d877-4c19-bcb4-bc1a9a2a5a38.png) і тд

Все наш html доступний за посиланням http://54.146.137.119/

Щоб перевірити чи все працює давайте подивимося на початковий стан сторінки

![image](https://user-images.githubusercontent.com/113981423/201425380-e459a9bb-3323-4417-917a-ce4983650d72.png)

Робимо зміни

![image](https://user-images.githubusercontent.com/113981423/201425775-85f4c3ab-e633-4ddf-9e9a-4e3418a116f3.png)

Комітимо і чекаємо поки все збілдиться

![image](https://user-images.githubusercontent.com/113981423/201425831-2d56406f-b7fb-4482-bdef-de70667eaf0d.png)

Бачимо що всі наші зміни автоматично задеплоїлися

![image](https://user-images.githubusercontent.com/113981423/201425898-4e3f35c4-6fb6-4379-9936-a30416435a0c.png)

Висновок: отже на цій лабораторній роботі я зміг ознайомитися з git action і CI/CD та на практиці його реалізувати.





