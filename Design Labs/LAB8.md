# Лабораторна робота №8
## **UI-компоненти інтерфейсу: кнопки, форми та їх стани. Побудова інтерактивного UI Kit у Figma**   

---

## **Мета роботи:** 

Ознайомитися з основними UI-компонентами інтерфейсу;
Навчитися проєктувати кнопки, чекбокси, радіобатони та інпут-поля;
Дослідити стани компонентів (default, hover, active, disabled, focus);
Розробити систему компонентів у складі UI Kit;
Навчитися використовувати варіанти (Variants) у Figma;
Інтегрувати компоненти у власний інтерфейс;
Використати інструменти ШІ для генерації ідей або текстів для UI..


---

## **Матеріальне забезпечення занять:**

1. Персональний комп'ютер, доступ до мережі Інтернет  
2. Обліковий запис Google  
3. Середовища Figma та FigJam.

---

## **Завдання для попередньої підготовки.**

1. Зробіть короткий словник (5-7 термінів) базових понять англ. мовою. 

| Term            | Definition                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| Button          | A clickable UI element that triggers an action when pressed.               |
| Input Field     | An area where users can enter text or data.                                |
| Toggle (Switch) | A control used to switch between two states, typically on and off.         |
| Checkbox        | A selection control that allows users to choose one or multiple options.   |
| Radio Button    | A control that allows users to select only one option from a group.        |
| State           | A visual or functional condition of a UI component (e.g., default, hover). |
| UI Kit          | A collection of reusable UI components and styles for consistent design.   |

2. Дайте відповіді на наступні питання:

**Які існують типи кнопок у UI-дизайні?**  
У UI-дизайні існують різні типи кнопок, які виконують різні ролі у взаємодії користувача з інтерфейсом. Основними є **Primary** — основна кнопка, яка виділяється та позначає головну дію на сторінці; **Secondary** — другорядна кнопка для менш пріоритетних дій; **Tertiary** або текстові кнопки, які використовуються для менш помітних дій; **Icon button**, що представлена у вигляді іконки, та **Ghost / Outline button**, яка має прозорий фон і контур, надаючи менш агресивний вигляд.

**Чим відрізняється checkbox від radio button?**  
Checkbox і radio button схожі зовні, але відрізняються логікою використання. **Checkbox** дозволяє обирати кілька варіантів одночасно, що підходить для множинного вибору. Натомість **radio button** обмежує користувача лише одним вибором у групі, забезпечуючи однозначне рішення.

**Чому важливо проєктувати стан "Disabled" для кнопок?**  
Проєктування стану "Disabled" для кнопок є важливим, оскільки він візуально показує, що дія наразі недоступна. Це зменшує ризик помилок користувача, пояснює, що потрібно виконати перед активацією, і робить інтерфейс більш зрозумілим та передбачуваним.

**Що таке стани компонентів і навіщо вони потрібні?**  
Стани компонентів — це різні візуальні та функціональні варіанти елемента, такі як default, hover, active, focus чи disabled. Вони допомагають надавати користувачу зворотний зв’язок, покращують взаємодію та роблять досвід користування передбачуваним і комфортним.

**Що таке "Focus state" і як він впливає на доступність (Accessibility)?**  
Focus state виникає, коли елемент вибрано за допомогою клавіатури, наприклад через клавішу Tab. Він критично впливає на доступність, оскільки допомагає користувачам, які не можуть використовувати мишу, орієнтуватися в інтерфейсі. Крім того, правильно спроектований Focus state забезпечує відповідність стандартам доступності, таким як WCAG, і робить продукт дружнім для людей з порушеннями зору або моторики.
    
---

# **Хід роботи**

[FigJam](https://www.figma.com/board/dn2rwEOPIhqGGgYHQha6M4/Untitled?node-id=0-1&t=IWmU83v8dYcyIlZw-1)
[Figma Icons](https://www.figma.com/design/z0sfijmBcM30ChN1JVnysx/Icons?t=QS15Fmf5smYuNER7-0)
[Figma App](https://www.figma.com/make/TyOGoO5Qh7GYu7zO1kxTR4/Frames?p=f&t=c5OqdPyjFACLuw5U-0&fullscreen=1)
[Figma AI Icons](https://www.figma.com/make/LuAY7dMGhgnpGEM0grOxWO/AI-Icons?p=f&t=XElzhf5ErWchSa59-0&fullscreen=1)

---

## **Контрольні запитання**

**Де в інтерфейсі доцільно розміщувати Placeholder, а де Label?**  
**Label** - це постійна назва поля, яка розміщується зверху або зліва від поля вводу, щоб користувач завжди бачив, що потрібно вводити. **Placeholder** — це підказка всередині поля, яка зникає, коли користувач починає вводити текст. Label використовується для постійної орієнтації та доступності, тоді як Placeholder допомагає швидко зрозуміти формат або приклад введення, але не замінює Label.

**Який розмір "області натискання" (Click target) вважається мінімально допустимим для мобільних пристроїв?**  
Мінімальний розмір області натискання для мобільних екранів за рекомендаціями зручності використання складає **44x44 пікселі**, що забезпечує комфортне натискання пальцем і зменшує ризик випадкових дотиків.

**Яку роль відіграє іконка в полі вводу (наприклад, "око" у полі пароля)?**
Іконка в полі вводу служить для підвищення зручності та зрозумілості. Наприклад, іконка **"око" у полі пароля** дозволяє тимчасово показати введений текст, щоб користувач міг перевірити правильність введення, не помиляючись у символах. Це покращує взаємодію та знижує ймовірність помилок.

---

### Conclusion

Designing user interfaces with clear components, states, and accessibility in mind ensures a seamless and intuitive experience. Proper use of buttons, input fields, labels, placeholders, and icons enhances usability, while well-defined states such as hover, active, disabled, and focus provide necessary feedback to users. Attention to accessibility, including appropriate click target sizes and focus indicators, makes interfaces inclusive for all users. Overall, a consistent and thoughtful UI design improves efficiency, reduces errors, and creates a positive user experience.
