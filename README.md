# A JavaScript RSA algorithm
___

> ВНИМАНИЕ! Этот модуль является решением для университетской лабораторной работы. Код был написан исключительно в учебных целях. Не используйте его в производстве!

Данный модуль предоставляет инструмент для шифрования криптографическим алгоритмом RSA, с генерацией ключей и функциями для шифрования, дешифрования, кодирования и декодирования строк.

## Пример использования
___

```JavaScript
const RSA = require('./rsa');

const message = 'Rivest, Shamir, Adleman';

const keys = RSA.generate(250);

console.log('Ключи');
console.log('Публичный:', keys.n.toString());
console.log('Приватный:', keys.d.toString());
console.log('Публичная экспонента:', keys.e.toString());

const encoded_message = RSA.encode(message);
const encrypted_message = RSA.encrypt(encoded_message, keys.n, keys.e);
const decrypted_message = RSA.decrypt(encrypted_message, keys.d, keys.n);
const decoded_message = RSA.decode(decrypted_message);

console.log('Сообщение:', message);
console.log('Закодированное:', encoded_message.toString());
console.log('Раскодированное:', decoded_message.toString());
console.log('Зашифрованное:', encrypted_message.toString());
console.log('Расшифрованное:', decrypted_message.toString());
```
