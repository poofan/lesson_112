# Магазин Подарков (Gift Store)

Простое REST-приложение на основе Spring Boot для управления подарками. Приложение реализует базовые CRUD-операции для сущности `Gift` и тесты с использованием MockMvc.

## Функциональность
- **CRUD-операции** для сущности `Gift`:
  - Создание подарка
  - Получение списка всех подарков
  - Получение информации о конкретном подарке по ID
  - Обновление подарка
  - Удаление подарка
- **In-memory хранилище** для хранения данных (без использования базы данных).
- **Тестирование контроллеров** с использованием MockMvc.

## Требования
- **Java 17** или выше
- **Maven 3.6+**
- **Spring Boot 3.1.0** или совместимая версия

## Установка и запуск
1. **Клонируйте репозиторий:**
   ```bash
   git clone https://github.com/ваш-аккаунт/gift-store.git
   cd gift-store
   ```
2. **Соберите проект:**

```bash
mvn clean install
```
3. **Запустите приложение:**

```bash
mvn spring-boot:run
```
4. **Приложение будет доступно по адресу:**

```arduino
http://localhost:8080
```
## API Эндпоинты
Получить список всех подарков
```bash
GET /api/gifts
```
Ответ:

```json
[
  {
    "id": 1,
    "name": "Мягкая игрушка",
    "description": "Плюшевый мишка"
  }
]
```
Получить подарок по ID
```bash
GET /api/gifts/{id}
```
Ответ (пример):

```json
{
  "id": 1,
  "name": "Мягкая игрушка",
  "description": "Плюшевый мишка"
}
```
Создать новый подарок
```bash
POST /api/gifts
Content-Type: application/json
```
Тело запроса:

```json
{
  "name": "Книга",
  "description": "Сказки Андерсена"
}
```
Ответ:

```json
{
  "id": 2,
  "name": "Книга",
  "description": "Сказки Андерсена"
}
```
Обновить подарок
```bash
PUT /api/gifts/{id}
Content-Type: application/json
```
Тело запроса:

```json
{
  "name": "Обновленный подарок",
  "description": "Новое описание"
}
```
Ответ:

```json
{
  "id": 1,
  "name": "Обновленный подарок",
  "description": "Новое описание"
}
```
Удалить подарок
```bash
DELETE /api/gifts/{id}
```
Ответ:

```css
204 No Content
```
## Тестирование
Для запуска тестов:

```bash
mvn test
```
Структура проекта
```bash
src/main/java/homework112/
    ├── controller/
    │   └── GiftController.java       # REST-контроллер
    ├── model/
    │   └── Gift.java                 # Сущность Gift
    ├── service/
    │   ├── GiftService.java          # Интерфейс сервиса
    │   └── GiftServiceImpl.java      # Реализация сервиса
    ├── repository/
    │   └── GiftRepository.java       # In-memory репозиторий
    └── App.java                      # Главный класс приложения
src/test/java/homework112/
    └── GiftControllerTest.java       # Тесты контроллеров
```
