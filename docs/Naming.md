## Part I. Нейминг

### 0. Ветки на github

Ветка должна называться deadline_<номер дедлайна>. Дедлайны нумеруются с 0. Пример - `deadline_0`

### 1. Общие правила

+ Название переменной должно отражать смысл этой переменной
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
const char* LONG_DELIMITER_ARGUMENT = "--delimiter"; // плохо, нару
const char* kLongDelimiterArgument = "--delimiter"; // хорошо
```

### 4. Функции и методы

+ Функции и методы должны называться в `PascalCase`([google](https://google.github.io/styleguide/cppguide.html#Function_Names))
+ Имя функции(метода) должно содержать глагол и не должно быть существительным

```C++
Options Parsing(int argc, char** argv) { 
  // плохо, не называйте функции существительными
}

Options ParseArguments(int argc, char** argv) {
  // хорошо
}
```

