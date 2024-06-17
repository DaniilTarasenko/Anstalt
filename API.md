| Read |  |
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
```
| Create |  |
| --- | --- |
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
```
| Update |  |
| --- | --- |
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
```
| Delete |  |
| --- | --- |
| Endpoint | DELETE /servers/{server_id} |
| Description | Удаление сервера |
| Request | N/A |
| Response | 
```
interface Response {}
```
| Execute |  |
| --- | --- |
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
```
| Enable root |  |
| --- | --- |
| Endpoint | POST /servers/{server_id}/enable_root |
| Description | Включение прав root на сервере |
| Request | N/A |
| Response | 
```
interface Response {}
```
| Disable root |  |
| --- | --- |
| Endpoint | POST /servers/{server_id}/disable_root |
| Description | Выключение прав root на сервере |
| Request | N/A |
| Response | 
```
interface Response {}
```
| Errors |  |
| --- | --- | 
| • ERR_USER_NOT_AUTH | пользователь не авторизован в приложении |
| • ERR_VALIDATION_FAILED | переданы невалидные входные параметры |
| • ERR_SERVER_NOT_FOUND | сервер не найден |
| • ERR_COMMAND_FAILED | выполнение команды завершилось ошибкой |
