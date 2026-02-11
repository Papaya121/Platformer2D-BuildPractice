# Platformer2D-BuildPractice

Проект для практики автоматической сборки Unity-проекта и работы с WebGL Template.

## О проекте

Проект включает:

* Скрипт автоматической сборки под PC и Android
* Кастомный WebGL Template
* Сборку WebGL-билда для запуска в браузере


---

## Build All

### Реализация

Добавлен Editor-скрипт:

```
Assets/Editor/BuildAll.cs
```

В Unity появляется пункт меню:

```
Build → Build All
```

При вызове:

1. Автоматически собирается билд под Windows или MacOS в зависимости от платформы
2. Затем выполняется сборка Android (.apk)
2. После запускается сборка WebGL

### Выходные файлы

Билды сохраняются в папку:

```
Builds/
 ├── Desktop/
 ├── WebGL/
 └── Android/
```

---

## WebGL Build с кастомным шаблоном

### Структура шаблона

```
Assets/WebGLTemplates/CustomTemplate/index.html
```

Используется кастомный HTML-шаблон на основе стандартного Unity WebGL Template с дополнительным элементом:

* Фиксированная надпись поверх canvas

### Особенности

* Надпись отображается поверх игры
* Поддерживается корректная загрузка loader/data/framework/wasm
* Работает на desktop и mobile
* Не нарушена стандартная логика Unity WebGL

---

## Сборка WebGL

1. Переключить платформу на WebGL
2. В Player Settings выбрать:

   ```
   WebGL Template → CustomTemplate
   ```
3. Выполнить Build

После сборки в папке билда используется кастомный HTML-шаблон.
