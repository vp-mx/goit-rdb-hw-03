# goit-rdb-hw-03

## 1. Вибірки з таблиць

a) Вибрати всі стовпчики (за допомогою wildcard `*`) з таблиці `products`:

```mysql
SELECT *
FROM products;
```

b) Вибрати тільки стовпчики `name`, `phone` з таблиці `shippers`:

```mysql
SELECT name, phone
FROM shippers;
```

## 2. Агрегати (AVG, MAX, MIN)

Знайти середнє, максимальне та мінімальне значення стовпчика `price` у таблиці `products`:

```mysql
SELECT AVG(price) AS avg_price,
       MAX(price) AS max_price,
       MIN(price) AS min_price
FROM products;
```

## 3. Унікальні значення та сортування

Оберіть унікальні значення колонок `category_id` та `price`, відсортуйте за спаданням `price` та виведіть лише 10
рядків:

```mysql
SELECT DISTINCT category_id, price
FROM products
ORDER BY price DESC LIMIT 10;
```

## 4. Підрахунок рядків у діапазоні цін

Знайти кількість продуктів (рядків), які знаходяться в цінових межах від 20 до 100 (включно):

```mysql
SELECT COUNT(*) AS products_count
FROM products
WHERE price BETWEEN 20 AND 100;
```

## 5. Групування за постачальником

Знайти кількість продуктів та середню ціну (`price`) у кожного постачальника (`supplier_id`):

```mysql
SELECT supplier_id,
       COUNT(*)   AS products_count,
       AVG(price) AS avg_price
FROM products
GROUP BY supplier_id;
```
