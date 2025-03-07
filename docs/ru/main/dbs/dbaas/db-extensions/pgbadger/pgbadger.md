**pgBadber** -- программа для анализа логов PostgreSQL для выявления потенциальных проблем с базой данных. Расширение с определенной периодичностью создает отчеты в формате HTML и складывает их в объектное хранилище. Пользователи также могут настроить ротацию отчетов.

Больше информации об использовании расширения можно найти на странице [документации расширения](https://github.com/darold/pgbadger).

#### Параметры, применимые в инфраструктуре VK Cloud:

| Название                     | Описание                                                                                                                                                                   | Пример                        |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| `period`                     | Периодичность создания отчетов (в часах), по умолчанию -- 24 часа.                                                                                                         | `--period="24"`               |
| `s3_bucket`                  | Имя существующего бакета объектного хранилища, в который будут складываться отчеты. Отчеты будут складываться в подпапки бакета, названные по id соответсвующего инстанса. | `--s3_bucket="pdbadger_logs"` |
| `log_min_duration_statement` | Минимальная длительность логируемого SQL-запроса (в миллисекундах). По умолчанию - 0 (логировать все запросы), -1 - не логировать                                          |
| ничего.                      | `--log_min_duration_statement="0"`                                                                                                                                         |
| `log_rotation`               | За сколько дней хранить отчеты, более старые отчеты будут удаляться. По умолчанию - 0 (ничего не удалять).                                                                 | `--log_rotation="0"`          |
