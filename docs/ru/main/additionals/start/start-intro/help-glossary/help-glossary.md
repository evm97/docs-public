Есть много терминов, специфичных для облачной инфраструктуры, которые часто плохо определены. Эта статья предоставляет некоторые подробности об аспектах терминологии, а также некоторых концепциях для лучшего понимания.

## Инстанс (Instance)

Термин "инстанс" часто используется для простого разговора о серверах в службе облачных вычислений, которые используются как услуга.

Инстанс - это облачный сервер, созданный из образа операционной системы и конфигурации виртуальной машины ("Flavor") (см. Ниже).

## Образ (Image)

Образ - это предустановленная, готовая к использованию операционная система. Это может быть дистрибутив Linux, операционная система Windows или любая другая система, предназначенная для работы на платформе облачных вычислений.

Эти образы могут быть «минимальными», то есть операционная система сводится к тому, что строго необходимо для стандартного использования. Они также могут быть оснащены предустановленными приложениями, чтобы пользователь мог избежать их переустановки при каждой перезагрузке инстанса.

Как правило, образы, используемые для облака, включают в себя некоторые инструменты настройки после запуска, которые можно использовать для установки информации, уникальной для экземпляра, например его имени хоста.

Существуют общедоступные образы, предоставляемые VK Cloud, и частные образы, созданные и загруженные индивидуально в каждом облачном проекте.

## Флейвор (Flavor) или Конфигурация виртуальной машины

Флейвор - это модель инстанса, определяющая его характеристики с точки зрения ресурсов. Флейвор определяет объем CPU и RAM виртуальной машины.

Например, флейвор "Standard-4-8" в облаке VK Cloud определяет 4 виртуальных CPU и 8 ГБ RAM.

## Диск (Volume)

Диск - это блочное устройство хранения данных, которые подключается к инстансам. В VK Cloud существует несколько разных типов дисков:  ssd, hdd и high-iops ssd.

Размер и тип дисков устанавливается индивидуально при их создании в соответствии с потребностями. Для дисков доступны операции расширения, присоединения, конвертирования, создания снимка или удаления.

## Зона доступности (Availability Zone)

Зона доступности — логическое деление и объединение гипервизоров для физической их изоляции и обеспечения отказоустойчивости. MS1 и DP1 — зоны, физически расположены в разных дата-центрах.

## Ключевая пара (Key pair)

Ключевая пара используется для входа на виртуальную машину с ОС Linux по протоколу ssh или для расшифровки пароля Windows инстанса. Ключевую пару можно создать в момент запуска инстанса или импортировать уже существующую.

## Группа безопасности (Security Group)

Это наборы настраиваемых разрешающих правил, которые регулируют права сетевого доступа (вход по определенному протоколу, через конкретный порт) для определенных IP адресов или групп безопасности.

## Гипервизор (Hypervisor)

Гипервизор - это программное обеспечение, которое создает и запускает виртуальные машины (ВМ). Гипервизор, иногда называемый монитором виртуальной машины (VMM), который изолирует операционную систему и ресурсы гипервизора от виртуальных машин и позволяет создавать и управлять этими виртуальными машинами
