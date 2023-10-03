## Part I. Нейминг

### 0. Ветки на github

Ветка должна называться deadline_<номер дедлайна>. Дедлайны нумеруются с 0. Пример - `deadline_0`

### 1. Общие правила

+ Название переменной должно отражать смысл этой переменной
+ Название не должно быть слишком коротким или слишком длинным
+ Название должно нести в себе достаточно информации для того, чтобы в текущем контексте можно было понять, что делает (за что отвечает) сущность названная таким образом
+ Сокращения это зачастую плохо

```C++
int l = 23; // плохо, не понятно, за что отвечает эта переменная
int nolfe = -1; // плохо, не используйте сокращения
```

### 2. Переменные

+ Имя переменной это обычно существительное или прилагательное, но точно не глагол
+ Имя переменной должно быть в `snake_case` ([google](https://google.github.io/styleguide/cppguide.html#Variable_Names))

```C++
int parse = 2023; // плохо, имя переменной должно быть существительным
int numberOfLines = 0; // плохо, имя должно быть в snake_case
```

+ _Булевы_ переменные лучше называть с префиксом `is_`, `can_`, `have_` и т.п.

```C++
bool work = true;
if (work) { // плохо
  ... 
}

bool is_working = true;
if (is_working) // хорошо, читается как обычный текст на английском
```

### 3. Константы

Константы называем в `PascalCase` с префиксом `k` ([google](https://google.github.io/styleguide/cppguide.html#Constant_Names))

```C++
const char* LONG_DELIMITER_ARGUMENT = "--delimiter"; // плохо
const char* kLongDelimiterArgument = "--delimiter"; // хорошо
```

### 4. Функции и методы

+ Функции и методы должны называться в `PascalCase` ([google](https://google.github.io/styleguide/cppguide.html#Function_Names))
+ Имя функции (метода) должно содержать глагол и не должно быть существительным

```C++
Options Parsing(int argc, char** argv) { 
  // плохо, не называйте функции существительными
}

Options ParseArguments(int argc, char** argv) {
  // хорошо
}
```

+ Функции, возвращающие `bool`, лучше называть с префиксом `Is`, `Can`, `Have` и т.п. по аналогии с переменными.

### 5. Структуры и классы

+ Структуры и классы должны называться в `PascalCase` ([google](https://google.github.io/styleguide/cppguide.html#Type_Names))
+ Имя структуры (класса) должно быть существительным и должно описывать объект, а не процесс

```C++
struct Parse {
  // плохо
}

struct Parsing {
  // плохо
}

struct ParseOptions {
  // хорошо
}
```

### 6. Перечисления

+ Для перечислений лучше использовать `enum class`, а не просто `enum` ([SOF](https://stackoverflow.com/questions/18335861/why-is-enum-class-preferred-over-plain-enum))
+ Каждый элемент перечисления должен именоваться также, как и константа. Само перечисление именуется также, как и структура

```C++
enum class error_code { // плохо
  NO_FILENAME,
  nofilename,
  no_filename,
};

enum class ErrorCode { // хорошо
  kNoFilename,
  kIncorrectDelimiter,
  kIncorrectLinesNumber,
};
``` 

### 7. Магические константы

Не используйте в коде числа (а также строки и т.д.), если нельзя __очень просто__ понять что они значат. Их стоит выносить в константы.

```C++
for (uint8_t i = 65; i <= 90; i++) { // плохо
    std::cout << static_cast<char>(i) << " ";   
}

// хорошо
const uint8_t ASCII_CODE_UPPER_A = 65;
const uint8_t ASCII_CODE_UPPER_Z = 90;
    
for (uint8_t i = ASCII_CODE_UPPER_A; i <= ASCII_CODE_UPPER_Z; i++) {
    std::cout << static_cast<char>(i) << " ";   
}
```

Во втором примере сразу понятно, что мы выводим в одну строку через пробел все большие буквы английского алфавита.
