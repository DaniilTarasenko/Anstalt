| Управление серверами |  |
| --- | --- |
| Endpoint | GET /servers |
| Description | Получение списка доступных серверов |
| Request | N/A |
| Response | 
```
interface Response {
  servers: Server[];
}

interface Server {
  id: string;
  name: string;
  ip: string;
  status: string;
}
``` |
| Endpoint | POST /servers |
| Description | Добавление нового сервера для управления |
| Request | 
```
interface Request {
  name: string; // min: 1; max: 160 символов
  ip: string;
}
```
| Response | 
```
interface Response {}
``` |
| Endpoint | PUT /servers/{server_id} |
| Description | Редактирование информации о сервере |
| Request | 
```
interface Request {
  name: string; // min: 1; max: 160 символов
  ip: string;
}
```
| Response | 
```
interface Response {}
``` |
| Endpoint | DELETE /servers/{server_id} |
| Description | Удаление сервера |
| Request | N/A |
| Response | 
```
interface Response {}
``` |
| Endpoint | POST /servers/{server_id}/commands |
| Description | Выполнение команды на сервере |
| Request | 
```
interface Request {
  command: string;
}
```
| Response | 
```
interface Response {
  output: string;
}
``` |
| Endpoint | POST /servers/{server_id}/enable_root |
| Description | Включение прав root на сервере |
| Request | N/A |
| Response | 
```
interface Response {}
``` |
| Endpoint | POST /servers/{server_id}/disable_root |
| Description | Выключение прав root на сервере |
| Request | N/A |
| Response | 
```
interface Response {}
``` |
| Errors | 
• ERR_USER_NOT_AUTH - пользователь не авторизован в приложении
• ERR_VALIDATION_FAILED - переданы невалидные входные параметры
• ERR_SERVER_NOT_FOUND - сервер не найден
• ERR_COMMAND_FAILED - выполнение команды завершилось ошибкой |
