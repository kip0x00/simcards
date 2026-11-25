SimCards — учет SIM-карт
========================

Веб-сервис показывает, где находятся SIM-карты: на оборудовании (системе)
или у сотрудника.

Запуск
------
Windows:
    simcards.exe

Linux:
    chmod +x simcards
    ./simcards

После запуска откройте http://localhost:33004
При первом запуске будет предложено создать администратора.

Каталоги и файлы
----------------
config.json		настройки (создается при первом запуске)
data/simcards.db	база данных SQLite
logs/			журналы по дням
update/			каталог для файлов обновления

Настройки (config.json)
-----------------------
web.port			порт веб-сервера, по умолчанию 33004
web.allowed_ips	список IP или CIDR, которым разрешён доступ
				(пустой список — всем; 127.0.0.1 и ::1 разрешены всегда)
log.level			уровень логирования: debug, info, warn, error

Администрирование
-----------------
Страница /admin доступна пользователям с ролью admin:
пользователи, роли, включение/отключение входа и журнал аудита.

Установка как служба
--------------------
Windows (командная строка от администратора):
    simcards.exe install
    simcards.exe start
    simcards.exe stop
    simcards.exe uninstall

Linux (от root):
    ./simcards install
    ./simcards start
    ./simcards stop
    ./simcards uninstall

Перед обновлением остановите службу и сохраните data/simcards.db.
