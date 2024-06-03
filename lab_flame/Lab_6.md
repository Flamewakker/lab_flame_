# Цель работы

Целью этой работы является выполнение тестирования API нашего серверного приложения, написанного с помощью Node.js. Эта работа включает в себя создание автоматических тестов, выбор подходящих инструментов и методов и составление отчета о результатах тестирования.

# Описание подхода к тестированию

Для тестирования выбрана среда Node.js из-за ее простоты использования и удобства в написании автотестов. В использовании следующие библиотеки:

- **Mocha.js** – для написания тестов.
- **Chai.js** – библиотека для утверждений (assertions), используется для проверки результата теста.
- **Supertest** – для комплексного тестирования HTTP запросов.
- **Faker.js** - для создания тестовых данных в виде различного типа строк.

Наши подходы к автоматическому тестированию включают проверку кода статуса в HTTP-ответах, валидацию формата и данных ответа, и проведение тестирование с переменными входными параметрами.

# Написание автотестов

Наше тестирование приватного API будет включать в себя следующие тестовые сценарии:

1. **Тест на успешный запрос**- Этот тест будет проверять, что запрос к API возвращает успешный код статуса при корректном запросе.
2. **Тест на некорректный запрос** - Данный тест проверяет что запрос с некорректными данными возвращает код статуса ошибки (например, 400 или 404, в зависимости от ситуации).
3. **Тест на валидацию данных** - Эта проверка тестирует, что API-ответ возвращает корректные и ожидаемые данные.
4. **Тест запросов, требующих аутентификацию** - Данный тест проверяет, что в случае запроса к приватному API-пути, происходит успешная аутентификация и возврат корректных результатов.

# Предположительная реализация автотестов

```javascript
const request = require('supertest');
const expect = require('chai').expect;
const faker = require('faker');

const app = require('../index.js');

describe('API Tests', function() {

  it('should make HTTP request and return successful status code', function(done) {
    request(app)
      .get('/api/public-resource')
      .end(function(err, res) {
        expect(res.statusCode).to.equal(200);
        done();
      });
  });

  it('should return error for invalid request', function(done) {
    request(app)
      .get('/api/invalid-endpoint')
      .end(function(err, res) {
        expect(res.statusCode).to.equal(404);
        done();
      });
  });

  it('should validate data', function(done) {
    request(app)
      .get('/api/public-resource')
      .end(function(err, res) {
        expect(res.body).to.have.property('data');
        done();
      });
  });

  it('should authenticate for private resources', function(done) {
    let username = faker.internet.userName();
    let password = faker.internet.password();
    request(app)
      .get('/api/protected-resource')
      .auth(username, password)
      .end(function(err, res) {
        expect(res.statusCode).to.equal(200);
        done();
      });
  });

});
```

# Выводы работы

Проведенное автоматическое тест