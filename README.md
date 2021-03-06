# Тестовое задание для front-end разработчика (VueJS)
### Что нужно использовать:
- VueJS
- Vuex
- Vue-Router
- Любовь к JS
- Внешние библиотеки, css-фреймворки, черная магия - **на Ваше усмотрение**

### Что хочется получить:

- Ссылку на **github** репозиторий с **подробной инструкцией**, как это дело запустить и потыкать
- Максимальный срок выполнения - **3 дня**

### Что нужно сделать:
Основываясь на конкретных входных данных необходимо разработать приложение отображающее список новостей, детальную страницу конкретной новости и комментарии к ней с возможностью их оценки.

| Маршрутизация приложения ||
| ------------- | ------------- |
| / | Главная страница с списком новостей |
| /news/{id} | Детальная страница конкретной новости. Параметр `id` - целое, положительное число |

Дополнительно к визуальным маршрутам для пользователя приложение должно обращаться к `API серверу`. 
Условное `API` должно отдавать в качестве ответа указанные ниже данные и **строго в том виде, в котором они указаны здесь**, даже если кто-то, *чисто теоретически*, ошибся. 

Создание заглушки с упаковкой данных в `.json` файлы - приветствуется. Вдруг условный разработчик еще не сделал API, но формат данных уже согласован.

В приложении должна быть предусмотрена возможность выставлять оценку комментарию. **Указанная / измененная оценка должна сохраняться на стороне приложения**.

**Все необходимые на Ваш взгляд данные - должны быть отображены, чего бы это не стоило.**

#### Список новостей (/api/v1/news) :GET
```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "Релиз 1.0",
      "images": {
        "icon": "https://vuejs.org/images/logo.png",
        "preview": null
      },
      "description": "<b>Доброго времени суток!</b><br/>Представляем релиз: <b>#1.0</b>",
      "createdAt": "2020-04-01 12:00:00",
      "author": {
        "title": "Александр Репин",
        "link": "/users/arepin"
      }
    },
    {
      "id": 2,
      "title": "Релиз 1.1",
      "images": {
        "icon": "https://vuejs.org/images/logo.png",
        "preview": "https://vuejs.org/images/logo.png"
      },
      "description": "VueJS: <img src=\"https://vuejs.org/images/logo.png\">",
      "createdAt": "2020-04-01 13:00:00",
      "author": {
        "title": "Александр Репин",
        "link": "/users/arepin"
      }
    },
    {
      "id": 3,
      "title": "Релиз 2.0",
      "images": {
        "icon": null,
        "preview": null
      },
      "description": "Доброго времени суток!</b><br/>Представляем релиз: <b>#2.0</b>",
      "createdAt": "1009-04-01 01:00:00",
      "author": {
        "title": "",
        "link": "/users/arepin"
      }
    }
  ]
}
```

#### Список комментариев к новости (/api/v1/news/{id}/comments) :GET
```json
{
  "success": true,
  "data": [
    {
      "id": 1,
      "comments": [
        {
          "id": 1,
          "description": "<b>Круто!</b> Требуем новую версию!",
          "createdAt": "2020-04-02 13:22:00",
          "likes": 22,
          "dislikes": 0,
          "author": {
            "title": "Анонимный пользователь",
            "link": null
          }
        },
        {
          "id": 2,
          "description": "Дизлайк!",
          "createdAt": "2020-04-02 13:32:00",
          "likes": 0,
          "dislikes": 10,
          "author": {
            "title": "Николай Серченко",
            "link": "/users/nserchenko"
          }
        }
      ]
    },
    {
      "id": 2,
      "comments": []
    }
  ]
}
```
