# Набор функций для облегчения работы с командной строкой	
## Функции
* **hasCommand** - Считывает данные с порта в буфер. Возвращает *true*, если поступила новая команда, *false* - если в буфере пусто.
* **getCommand** - Возвращает текст введённой команды
* **getArg** - Возвращает текст следующего аргумента
* **getArgInt** - Возвращает значение следующего числового аргумента

## Использование
```c
#include <CommandLine.h>

void loop() {
	// Проверяем, поступила ли новая команда
	if(hasCommand()){
		// Считываем команду в переменную command
		const char *command = getCommand();

		// Если команда nunmer
		if(strcmp(command, "number") == 0){
				// Считываем следующий числовой аргумент
	      int number = getArgInt();
	      
	      Serial.print("Input number: ");
	      Serial.println(number);
	    }
	  // Если команда word
		else if(strcmp(command, "word") == 0){
				// Считываем слудеющий текстовой аргумент
	      char *word = getArg();

	      Serial.print("Input word: ");
	      Serial.println(word);
	    } else {
	      Serial.println("Invalid command");
	    }
	}
}
```
При вводе команды *number 123* будет возвращено *Input number: 123*.
При вводе *world is great* будет возвращено *Input word: is*.