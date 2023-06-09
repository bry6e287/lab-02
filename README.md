# lab-02

# Task 1

```
https://github.com/Vlad1kavkaz/lab-02.git
```
```
$ mkdir lb2
$ echo "# lb2" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git remote add origin https://github.com/Vlad1kavkaz/lab-02.git
$ git push -u origin master
```
## Создаем файл с плохим стилем кода
```
#include <iostream>

using namespace std;

int main(int argc, char** argv) {
   cout << "Hello world" << endl;
}
```

```
$ git add "Hello.cpp"
```

```
$ git commit -m "This is first file"
```

```
$ alias edit=subl
$ edit "Hello world.cpp"
#include <iostream>
#include <string>
 
using namespace std;

int main(int argc, char** argv) {
   string name;
   cin >> name;
   cout << "Hello world from " << name << endl;
}
```

```
$ git commit -a -m "Changed cpp file"
```

```
$ git push -u origin master
```

```
История дотупна в репозитории
```

#Task2

```
$ git checkout -b patch1
```

```
$ edit "Hello world.cpp"
#include <iostream>
#include <string>
 
int main(int argc, char** argv){
  string name;
  std::cin >> name;
  std::cout << "Hello world from " << name << std::endl;
}
```

```
$ git commit -a -m "Fixed cpp file"
$ git push -u origin patch1
```

```
Ветка патч2 доступна в репозитории
```

```
create a pull recvest
```

```
$ edit "Hello world.cpp"
#include <iostream>
#include <string>
 
int main(int argc, char** argv){
  string name;                                           // Name of user
  std::cin >> name;                                      // Input name of user
  std::cout << "Hello world from " << name << std::endl; // Output name of user
} 
```

```
$ git commit -a -m "Code with comments"
$ git push -u origin patch1
```

```
Изменения в пул реквесте есть
```

```
Объединяем патч2 с мастером и удаляем её
```

```
$ git pull origin
```

```
$ git log master
```

```
$ git branch -d patch1
```

#Task3

```
$ git checkout -b patch2
```

```
$ clang-format -i -style=Mozilla "hello world.cpp"
```

```
$ git commit -a -m "Changed code style in cpp file"
$ git push -u origin patch2
создаем пул реквест патч2 в мастера
```

```
$ git checkout master
$ edit "Hello world.cpp"
#include <iostream>
#include <string>
 
int main(int argc, char** argv){
  string name;                                           // имя пользователя
  std::cin >> name;                                      // ввод имени 
  std::cout << "Hello world from " << name << std::endl; // вывод имени
} 

$ git commit -a -m "Fixed cpp file"
$ git push -u origin patch2
```

```
В пул реквесте есть конфликты
```

```
$ git pull origin master
$ git rebase master
$ edit "Hello world.cpp"
$ git commit -a -m "Update code"
```

```
$ git pull origin master
$ git rebase master
$ edit "Hello world.cpp"
$ git commit -a -m "Update Hello world.cpp"
$ git rebase --continue
```

```
Конфликтов нет
```

```
Объединяем патч2 в мастера и удаляем патч2
```
