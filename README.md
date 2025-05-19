# week-11-15

Отчет об ошибках и их исправлениях

Проблема 1:
    Ошибка: "Database initialization error: [TypeError: Cannot read property 'execAsync' of undefined]"
    Причина: Способ инициализации реализованный на данный момент не совместим с последней версией EXPO SQLite
    Решение: Вместо метода-посредника db.withTransactionAsync проводить инициализацию напрямую

Проблема 2:
    Ошибка: "[TypeError: Cannot read property 'rows' of null]"
    Причина: execAsync не подразумевает возможность использования параметров
    Решение: Вместо execAsync использовать getAllAsync и runAsync, также проверять длину полученного массива, вместо количества rows

Проблема 3:
    Ошибка: "Warning: ReferenceError: Property 'Button' doesn't exist"
    Причина: execAsync не подразумевает возможность использования параметров
    Решение: Вместо execAsync использовать getAllAsync и runAsync, также проверять длину полученного массива, вместо количества rows