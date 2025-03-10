## Построение конечной точки

Чтобы работать с очередями Cloud Queues, необходимо использовать endpoint https://sqs.mcs.mail.ru/

## Региональные конечные точки

Каждая конечная точка Cloud Queues независима. Например, если две очереди названы MyQueue и одна имеет конечную точку sqs.ru-east-2.mcs.mail.ru, а другая - конечную точку sqs.mcs.mail.ru, эти две очереди не обмениваются данными друг с другом.

Ниже приведен пример конечной точки, которая делает запрос на создание очереди.

```
https://sqs.mcs.mail.ru/   
?Action=CreateQueue
&DefaultVisibilityTimeout=40
&QueueName=MyQueue
&Version=2012-11-05
&AUTHPARAMS
```

### Важно

Имена очередей и URL-адреса очередей чувствительны к регистру. Структура AUTHPARAMS зависит от подписи запроса API.

## Выполнение запроса GET

GET-запрос Cloud Queues структурирован как URL-адрес, который состоит из следующего:

- **Конечная точка** - ресурс, на который действует запрос ( имя очереди и URL-адрес ), например: https://sqs.mcs.mail.ru/123456789012/MyQueue
- **Действие** - действие, которое вы хотите выполнить на конечной точке. Знак вопроса (?) отделяет конечную точку от действия, например: ?Action=SendMessage&MessageBody=Your%20Message%20Text
- **Параметры** - любые параметры запроса - каждый параметр разделяется амперсандом (&), например: &Version=2012-11-05&AUTHPARAMS

Ниже приведен пример GETзапроса, который отправляет сообщение в очередь VK Cloud SQS.

```
https://sqs.mcs.mail.ru/123456789012/MyQueue
?Action=SendMessage&MessageBody=Your message text
&Version=2012-11-05
&AUTHPARAMS
```

### Важно

Имена очередей и URL-адреса очередей чувствительны к регистру.

Поскольку GETзапросы являются URL-адресами, вы должны URL-кодировать все значения параметров. Поскольку в URL-адресах нельзя использовать пробелы, каждый пробел кодируется как %20. (Остальная часть примера не закодирована в URL-адресе для облегчения чтения.)

## Выполнение запроса POST

POST Запрос Cloud Queues отправляет параметры запроса в виде формы в теле HTTP-запроса.

Ниже приведен пример заголовка HTTP со Content-Type значением application/x-www-form-urlencoded.

```
POST /123456789012/MyQueue HTTP/1.1
Host: sqs.mcs.mail.ru
Content-Type: application/x-www-form-urlencoded
```

За заголовком следует запрос, отправляющий сообщение в очередь Cloud Queues. Каждый параметр разделен амперсандом ( & ).

```
Action=SendMessage
&MessageBody=Your+Message+Text
&Expires=2020-10-15T12:00:00Z
&Version=2012-11-05
&AUTHPARAMS
```

### Важно

Content-Type требуется только заголовок HTTP. AUTHPARAMS так же, как и в GETзапросе. Ваш HTTP-клиент может добавлять другие элементы в HTTP-запрос в зависимости от версии HTTP-клиента.
