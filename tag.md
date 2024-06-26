## *Теги*

Теги — это ссылки, указывающие на определенные точки в истории Git.

Для создания нового тега выполните следующую команду:

```
git tag <tagname>
```

Замените < имя_тега > семантическим идентификатором состояния репозитория на момент создания тега. Стандартный шаблон для указания номеров версий выглядит как git tag v1.4.

Git поддерживает два типа тегов: аннотируемые и облегченные. 

Облегченные теги
 ---

```
git tag v1.4-lw
```

При выполнении этой команды создается облегченный тег с идентификатором v1.4-lw. 

Облегченные теги создаются, когда не используются параметры -a, -s или -m. Этот тип тегов создает новую контрольную сумму тега и сохраняет ее в каталоге .git/ репозитория проекта.


Аннотируемые теги
---

Аннотируемые теги хранятся в базе данных Git в виде полных объектов. 

Для обеспечения безопасности аннотируемые теги можно подписывать и проверять с помощью GNU Privacy Guard (GPG). 

Рекомендуется использовать аннотированные, а не облегченные теги, чтобы иметь доступ ко всем связанным метаданным.

```
git tag -a v1.4
```

При выполнении этой команды будет создан аннотируемый тег с идентификатором v1.4.

 Затем команда откроет настроенный текстовый редактор по умолчанию, чтобы запросить ввод дальнейших метаданных.

 ```
 git tag -a v1.4 -m "my version 1.4"
 ```
Эта команда аналогична предыдущей, однако в этой версии передаются параметр -m и комментарий. 

Этот удобный способ похож на команду git commit -m, так как с его помощью новый тег создается без открытия локального текстового редактора. Вместо этого применяется комментарий, переданный после параметра -m.

Просмотр списка тегов
---

Чтобы просмотреть список сохраненных в репозитории тегов, выполните следующую команду:

```
git tag
```

Она выведет список тегов:

```
v0.10.0
    v0.10.0-rc1
    v0.11.0
    v0.11.0-rc1
    v0.11.1
    v0.11.2
    v0.12.0
    v0.12.0-rc1
    v0.12.1
    v0.12.2
    v0.13.0
    v0.13.0-rc1
    v0.13.0-rc2
```

Чтобы уточнить список тегов, можно передать параметр -l и выражение с подстановочными знаками:

```
$ git tag -l *-rc*
    v0.10.0-rc1
    v0.11.0-rc1
    v0.12.0-rc1
    v0.13.0-rc1
    v0.13.0-rc2
    v0.14.0-rc1
    v0.9.0-rc1
    v15.0.0-rc.1
    v15.0.0-rc.2
    v15.4.0-rc.3
```

 В указанном выше примере используются параметр -l и выражение с подстановочными знаками -rc, возвращающее список всех тегов с префиксом -rc, который обычно используется для обозначения предвыпускных релизов.

### [Назад](/data.md)