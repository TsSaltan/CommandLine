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
  	// put your main code here, to run repeatedly:
	if(hasCommand()){
		const char *command = getCommand();

		if(strcmp(command, "number") == 0){
	      int number = getArgInt();
	      
	      Serial.print("Input number: ");
	      Serial.println(number);
	    }
		else if(strcmp(command, "word") == 0){
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