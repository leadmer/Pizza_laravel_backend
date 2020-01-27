# Серверная часть сайта доставки пицц

Здесь находится серверная часть задания для сайта доставки пиццы.
\
\
По пути app/ находятся два файла Order.php и Pizza.php это модели представления заказов и пицц в базе данных.
\
\
По пути app/Http/Controllers/Api лежат контроллеры для обработки запросов к этим моделям OrderController.php и PizzaController.php.
\
\
По пути database/migrations лежат миграции для пицц и заказов: 2020_01_23_115416_create_pizzas_table.php и 2020_01_23_192529_create_orders_table.php.
\
Возможные urls сервера находятся в файле routes/web.php. 
\
\
Так же в файле routes/api.php находятся urls пути api сервера: 
\
    - Route::get('pizza', 'Api\PizzaController@index') - get запрос, возвращает все пиццы, находящиеся в базе данных
    \
    - Route::get('pizza/{id}', 'Api\PizzaController@show') - get запрос, возвращает пиццц по уникальному id из базы данных
    \
    - Route::post('order', ['uses' => 'Api\OrderController@show', 'https']) - post запрос, записывает в базу данных оформленный заказ
    \
    - Route::get('order/{id}', 'Api\OrderController@show') - get запрос, возвращает заказ по уникальному id из базы данных
