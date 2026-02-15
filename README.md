Блок 1: Теория вероятности и логика

Задание 1: Фермер
    
    3,99


Задание 2: Кулинарное соревнование

    26,8


Задание 3: Одинокая дорога

    0,63; 0,93

Блок 2: Python

Задание 1: Изоморфизмы

    Время: O(n)
    Память: O(n)

    def is_isomorphic(s, t):
        if len(s) != len(t):
            return False

        map_st = {}
        map_ts = {}

        for c1, c2 in zip(s, t):
            if c1 in map_st and map_st[c1] != c2:
                return False
            if c2 in map_ts and map_ts[c2] != c1:
                return False

            map_st[c1] = c2
            map_ts[c2] = c1

        return True

Задание 2: Натуральная последовательность

    Время O(n)
    Память O(1)

    def missing_number(nums):
        n = len(nums) + 1
        expected_sum = n * (n + 1) // 2
        actual_sum = sum(nums)
        return expected_sum - actual_sum


Задание 3: Факторизация

    Время: O(√n)
    Память: O(log n)
    
    def prime_factors(n):
        factors = []
        while n % 2 == 0:
            factors.append(2)
            n //= 2
        
        i = 3
        while i * i <= n:
            while n % i == 0:
                factors.append(i)
                n //= i
            i += 2
        
        if n > 1:
            factors.append(n)

        return factors

Блок 3: SQL

Задание 1: Абитуриенты

    SELECT
        id,
        scores,
        ROW_NUMBER() OVER (ORDER BY scores DESC) AS position
    FROM examination;

Задание 2: FULL JOIN

    минимально 30 и максимально 50 строк

Задание 3: Покупки

    SELECT 
        a.client_id
    FROM account a
    JOIN transaction t 
        ON a.id = t.account_id
    WHERE 
        t.type = 'BUY'
        AND t.transaction_date >= CURRENT_DATE - INTERVAL '1 month'
    GROUP BY 
        a.client_id
    HAVING 
        SUM(t.amount) < 5000;

Блок 4: Статистика и АБ-тесты

Задание 1: Воодушевленное руководство
Ответ:
  
    1) Тест репрезентативен относительно своей генеральной совокупности: таких же небольших городов, можем применять только в подобных городах.
    2) Наличие эффекта подтвердило потенциал идеи, поэтому сразу применять по всем городам не будем, но можем провести эксперимент в других городах.

Задание 2: Основной показатель в статистике
Ответ:

    1) Вероятность наблюдения такого или более экстремального результата при условии, что нулевая гипотеза верна.

Задание 3: Параметрический тест
Ответ: 

    1) Да, можно, потому, что при большом объеме выборки распределение среднего будет недалеко от нормального 

Блок 5: ML Base

Задание 1: Пони тоже кони
Ответ:

    1) Возьму вторую модель, и инвертирую ее предсказания. Потому, что инвертированный показатель второй модели станет равен 0,9, что больше 0,7.

Задание 2: Ручной счёт ROC_AUC
Ответ:

    0,71

Задание 3: Ручной счёт корреляции
Ответ:

    0,9
