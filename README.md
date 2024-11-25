# Flutter
## _**Лекция 1**_
1. Установка Flutter<br>
Скачиваем flutter, распаковываем в {user_name}/dev/
2. установка значения Path<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок1.png)<br>
3. проверка flutter doctor<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок2.png)<br>
4. настройка android studio<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок4.png)<br>
5. установка и настройка VS Code<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок3.png)<br>
6. Проверка flutter doctor<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок9.png)<br>
7. обновление Visual Studio<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок8.png)<br>
8. Проверка flutter doctor<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок10.png)<br>
Итог:<br>
   Запуск в браузере:<br>
 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок6.png)<br>
 Запуск на эмуляторе:<br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок7.png)<br>
<br><br>
## _**Лекция 2**_
1. runApp <br>
```
void main() {
  runApp(
    Text(
        'Hello World',
        textDirection: TextDirection.ltr,
        textAlign: TextAlign.center,
    ),
  );
}
```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок11.png)<br>
  
```
void main() {
  runApp(
    Align(
      alignment: Alignment.center,
      child:Text(
          'Hello World',
          textDirection: TextDirection.ltr,
      ),
    ),
  );
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок12.png)<br>

2. MaterialApp <br>
Чтобы не усложнять посмотрим на изначальный пример кода, созданный автоматически и изменим цвет темы на blueGray и deepOrangeAncient для демонстрации свойства theme виджета MaterialApp <br>

```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.blueGrey),  //deepOrangeAncient
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});
  final String title;
  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text(widget.title),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ),
    );
  }
}
```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок13.png)<br>
  
  Можно также изменить заголовок<br>
  
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок14.png)<br>
  
3. Scaffold <br>

```
void main() {
  runApp(MaterialApp(
     home: Scaffold(
      body: Container(
        color: Colors.white,
        padding: EdgeInsets.only(top:25),
        child: Text("Hello World",
            style: TextStyle(fontSize: 22, color: Colors.black87),
            textDirection: TextDirection.ltr),
      ),
    ),
  ));
}
```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок15.png)<br>

```
void main() {
  runApp(MaterialApp(
     home: Scaffold(
      body: Container(
        color: Colors.deepOrange,
        padding: EdgeInsets.all( 25),
        child: Text("Hello World",
            style: TextStyle(fontSize: 30, color: Colors.black),
            textDirection: TextDirection.ltr),
      ),
    ),
  ));
}

```
<br>
  
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок16.png)<br>

4. Stateless Widget <br>
Для примера работы Stateless возьму код из видео-лекции <br>

```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyStatelessWidget(color: Colors.red));
}

class MyStatelessWidget extends StatelessWidget{
  const MyStatelessWidget({super.key, required this.color});
  final Color color;
  @override
  Widget build(BuildContext context) {  
    return Container(
      color: color
    );
  }
}
```
<br>
  
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок17.png)<br>
  
5. Stateful Widget <br>
   Изменю предыдущий код для демонстрации работыStateful
   <br>

 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок18.png)<br>

```
import 'package:flutter/material.dart';

void main() {
  runApp( MyStatelessWidget(color: Colors.red));
}

class MyStatelessWidget extends StatefulWidget{
  const MyStatelessWidget({super.key, required this.color});
  
  final Color color;

  @override
  State<MyStatelessWidget> createState() => _MyStatelessWidgetState();
}

class _MyStatelessWidgetState extends State<MyStatelessWidget> {
  late Color color;
  void initState(){
    super.initState();
    color=widget.color;
  }
  
  @override
  Widget build(BuildContext context) {  
    return GestureDetector( 
      onTap: () {
        setState(() {
                  color = Colors.green;
        });
      },
      child: Container(
        color: color
      ),
    );
  }
}
```
<br>
Теперь цвет заднего фона при нажатии меняет цвет на зелёный<br>

 ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок19.png)<br>

6. Работа с Asset и Image <br>
7. Работа с Asset и Font <br>





