[[Non-access модификаторы]]

_только для переменных_. Его рекомендуется использовать для переменных, которые могут быть одновременно использоваться несколькими потоками. Переменная с таким модификатором при каждом изменении моментально копируется из кэша процессора в основную память, позволяя параллельным потокам получать самое «свежее» значение.