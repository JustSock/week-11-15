# week-11-15

## Отчет об ошибках и их исправлениях

Проблема 1:
    **Ошибка:** "Database initialization error: [TypeError: Cannot read property 'execAsync' of undefined]"
    **Причина:** Способ инициализации реализованный на данный момент не совместим с последней версией EXPO SQLite
    **Решение:** Вместо метода-посредника db.withTransactionAsync проводить инициализацию напрямую

Проблема 2:
    **Ошибка:** "[TypeError: Cannot read property 'rows' of null]"
    **Причина:** execAsync не подразумевает возможность использования параметров
    **Решение:** Вместо execAsync использовать getAllAsync и runAsync, также проверять длину полученного массива, вместо количества rows

Проблема 3:
    **Ошибка:** "Warning: ReferenceError: Property 'Button' doesn't exist"
    **Причина:** Не импортирована Button из react-native
    **Решение:** Импортировать Button из react-native

Проблема 4:
    **Ошибка:** "Warning: React.jsx: type is invalid -- expected a string (for built-in components) or a class/function (for composite components) but got: object."
    **Причина:** Неподходящий формат ввода в компонент Camera
    **Решение:** Использовать CameraView вместо Camera

Проблема 5:
    **Ошибка:** Отсутствует возможность прокрутки
    **Причина:** Отсутствует ScrollView 
    **Решение:** Добавить ScrollView 

Проблема 6:
    **Ошибка:** VirtualizedLists should never be nested inside plain ScrollViews with the same orientation because it can break windowing and other functionality - use another VirtualizedList-backed container instead. [Component Stack]
    **Причина:** Элементы прокрутки накладываются друг на друга
    **Решение:** Отключить прокрутку на SwipeListView

Проблема 7:
    **Ошибка:** Кнопки залезают друг на друга
    **Причина:** Отсутствие отступов
    **Решение:** Добавить отступов 