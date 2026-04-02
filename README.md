# Лабораторная работа №20. Работа с DOM и событиями в JavaScript

**ФИО:** Черкина Дарья Алексеевна 
**Группа:** ИСП-231  
**Дата:** 01.04.2026

---

## Описание (что изучили)

В ходе лабораторной работы были изучены основы работы с DOM (Document Object Model) и событиями в JavaScript:

- Что такое DOM и как JavaScript взаимодействует с HTML-документом
- Поиск элементов по id и CSS-селекторам
- Изменение текстового содержимого и стилей элементов
- Обработка событий: клик, ввод, отправка формы
- Работа с HTML-формами и валидация данных
- Динамическое создание и удаление элементов
- Делегирование событий

---

## Структура проекта
- img
    - скрины
- README.md
- dynamicElements.html
- dynamicElements.js
- index.html
- main.js
- style.css


---

## Сравнение с C# (WinForms/WPF)

### DOM в JS = Controls в C# WinForms

| Концепция | C# (WinForms) | JavaScript (DOM) |
|---|---|---|
| Найти элемент | `Button myButton = this.Controls["myButton"]` | `const myButton = document.getElementById("myButton")` |
| Изменить текст | `label1.Text = "Новый текст"` | `label.textContent = "Новый текст"` |
| Добавить обработчик | `button1.Click += HandleClick` | `button.addEventListener("click", handleClick)` |
| Создать элемент | `Button btn = new Button()` | `const btn = document.createElement("button")` |
| Добавить в контейнер | `panel1.Controls.Add(btn)` | `panel.appendChild(btn)` |
| Скрыть элемент | `button1.Visible = false` | `button.style.display = "none"` |

---

### Events в JS = События в C#

**C# (WinForms):**

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    label1.Text = "Нажато!";
}
```

**JavaScript (DOM):**

```javascript
button.addEventListener("click", (e) => {
    label.textContent = "Нажато!";
});
```

---

### Валидация формы

**C# (WinForms):**

```csharp
private void SubmitButton_Click(object sender, EventArgs e)
{
    if (string.IsNullOrEmpty(nameTextBox.Text))
    {
        MessageBox.Show("Введите имя!");
        return;
    }
    // ...
}
```

**JavaScript (DOM):**

```javascript
form.addEventListener("submit", (e) => {
    e.preventDefault();

    if (!nameInput.value.trim()) {
        alert("Введите имя!");
        return;
    }
    // ...
});
```

---

### Главные отличия

| Аспект | C# WinForms | JavaScript DOM |
|---|---|---|
| Компиляция | Да | Нет (интерпретация) |
| Типизация | Строгая | Динамическая |
| Ошибки | Во время компиляции | Во время выполнения |
| UI-дизайнер | Есть (визуальный) | Нет (только код) |
| Платформа | Windows | Любой браузер |

---

### Преимущества DOM перед WinForms

- Кроссплатформенность (работает везде)
- Не нужна установка приложения
- Легко обновлять (обновил файлы — всё работает)
- Современные UI (CSS, анимации)

### Преимущества WinForms перед DOM

- Визуальный дизайнер (drag & drop)
- Ошибки на этапе компиляции
- Интеграция с Windows API
- Более понятная структура

---

**Вывод:** DOM и WinForms решают схожие задачи, но разными подходами.
