# АТД Занятие
## Данные
- Предмет
- Длительность
- Тип (лекция, практика, семинар, … )
- Аудитория
- Преподаватель
- Группа



## Операции
**Конструктор**

Начальные значения: -

*Процесс*:
          Предмет = «»
          Длительность = 0
          ….
                                   
         Операция ЗадатьПредмет
                • Вход: название_предмета
                • Предусловия: название_предмета не пустое
                • Процесс: Предмет = название_предмета
                • Выход: -
                • Постусловия: -
         
         Операция ПрочитатьПредмет
                • Вход: 
                • Предусловия: 
                • Процесс: прочитать Предмет
                • Выход: Предмет
                • Постусловия: -
                  
        Операция ЗадатьДлительность
                • Вход: длительность1
                • Предусловия: длительность1 > 0
                • Процесс: Длительность = длительность1
                • Выход: -
                • Постусловия: -
...
Конец Занятие


```C++
#include <string>
#include <stdexcept>

/// Занятие
class Lesson{
	private:
		std::string discipline;		// ..
		unsigned time;			// ..
		// ...

	public:
		// конструктор (инициализирует поля)
		Lesson(){
			discipline = "";
			time = 0;}

		/// ПрочитатьПредмет
		std::string get_discipline(){ return discipline;}

		/// Задать предмет
		void set_discipline(const std::string &discipline1){
			if (discipline1 == "")
				throw std::invalid_argument("Error: discipline1 is empty");
			discipline = discipline1;}

		/// ЗадатьДлительность
		void set_time(unsigned t){
			if ( t == 0) throw 
				std::invalid_argument("Error: t = 0");
			else
				time = t;}

		/// ЗадатьДлительность
		unsigned get_time(){ return time;}

		std::string to_string(){
			return discipline + "; time: " + std::to_string(time);
		}

};
```
