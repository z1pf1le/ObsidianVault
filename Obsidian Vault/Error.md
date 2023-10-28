[[Throwable]]

Error ошибки виртуальной машины.

StackOverflowError — возникает, например, когда метод бесконечно вызывает сам себя OutOfMemoryError — возникает, когда недостаточно памяти для создания новых объектов.
NoClassDefFoundError – не смог найти класс Error — это критическая ошибка во время исполнения программы, связанная с работой виртуальной машины Java.

В большинстве случаев Error не нужно обрабатывать, поскольку она свидетельствует о каких-то серьезных недоработках в коде.

Errors indicate abnormal situations that should never happen. An error is thrown when a serious problem has occurred. **Further, errors are regarded as unchecked exceptions, and applications should not try to catch and handle them**. Moreover, errors happen at run time and cannot be recovered.

