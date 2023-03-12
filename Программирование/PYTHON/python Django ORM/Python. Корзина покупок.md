## django_project/app/models.py

Вам даны модели корзины для покупок `ShoppingCart` и товара `ShopItem`. Наличие товаров в корзине будет описывать модель `ShoppingCartPosition`. Кроме связи корзины и товара нужно знать количество товаров в корзине, эта информация тоже должна храниться в `ShoppingCartPosition`. Должно быть невозможно добавить один и тот же товар в корзину дважды — это должно быть ограничение (constraint) на уровне БД.

Задачи:

-   Описать необходимые поля модели `ShoppingCartPosition`.
-   Сгенерировать миграции.
-   Реализовать метод `ShoppingCart.add()`, который должен добавлять товар в корзину в указанном количестве:
    
    ```
    cart = models.ShoppingCart.objects.create()
    apple = models.ShopItem.objects.create(name='apple', price=2.0)
    pear = models.ShopItem.objects.create(name='pear', price=3.0)
    cart.add(apple, 2)
    cart.add(pear)  # по умолчанию добавляется одна штука
    ```
    
-   Реализовать свойство `ShoppingCart.total_price`, которое должно возвращать суммарную стоимость товаров в корзине с учётом их количества:
    
    ```
    cart.total_price == 2 * 2.0 + 1 * 3.0 # True
    ```
    
-   Реализовать метод `ShoppingCart.preview()`, который должен возвращать итератор пар, каждая из которых состоит из наименования товара (строка) и количества товаров этого вида в корзине. Элементы итератора должны быть отсортированы по порядку **убывания итоговой цены** позиции в корзине: сотня салфеток ценой в 10коп каждая — 10руб в сумме — должна идти раньше пары яблок по 2руб за каждое или 4руб в сумме.
    
    ```
    for name, quantity in cart.preview():
        print(quantity, '×', name)
    
    # => 2 × apple
    # => 1 × pear
    # пара яблок дороже одной груши!
    ```
    

## Подсказка

-   Для `ShoppingCart.preview()` вам пригодятся аннотирование и [F-выражения](https://docs.djangoproject.com/en/3.0/ref/models/expressions/#f-expressions).
-   Для `ShoppingCart.total_price` вам пригодятся те же F-выражения и агрегация.
-   Чтобы обеспечить уникальность товаров в корзине, укажите для `ShoppingCartPosition` ограничение [unique_together](https://docs.djangoproject.com/en/4.1/ref/models/options/#unique-together).