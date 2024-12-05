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
   Изменю предыдущий код для демонстрации работы Stateful
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

Создание новой папки <br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок20.png)<br>
Добаление кода в файл yaml <br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок21.png)<br>
```
import 'package:flutter/material.dart';

void main() {
  runApp( MaterialApp(
    home: Scaffold(
appBar: AppBar(
  title: const Text('Title'),
  actions:[IconButton(onPressed: (){}, icon: const Icon(Icons.add))],
),
    body: MyStatelessWidget(color: Colors.red),
     floatingActionButton: IconButton(onPressed: (){}, icon: const Icon(Icons.add)),
)));
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
        color: color,
        child: Image.asset('assets/96.jpg'),
      ),
    );
  }
}

```
<br>
При копировании кода в yaml файл возникла ошибка<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок22.png)<br>
  
```
[flutter_application_3] dart pub get --no-example
Error on line 20, column 11 of pubspec.yaml: Mapping values are not allowed here. Did you miss a colon earlier?
   ╷
20 │     assets:
   │           ^
   ╵
exit code 65

```
<br>
после исправления ошибки<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок23.png)<br>
  
7. Работа с Asset и Font <br>
  Создаём папку для шрифтов и обновляем файл <br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок24.png)<br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок25.png)<br>

```
import 'package:flutter/material.dart';

void main() {
  runApp( MaterialApp(
    home: Scaffold(
appBar: AppBar(
  title: const Text('Title', style: TextStyle(fontFamily: 'Raleway', fontSize: 10),),
  actions:[IconButton(onPressed: (){}, icon: const Icon(Icons.add))],
),
    body: MyStatelessWidget(color: Colors.red),
     floatingActionButton: IconButton(onPressed: (){}, icon: const Icon(Icons.add)),
)));
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
        color: color,
        child: Image.asset('assets/96.jpg'),
      ),
    );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок26.png)<br>


## _**Лекция 3**_  
1.UniqueKey<br>

```
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  runApp(const MaterialApp(
    home: PositionedTile(),
  ));
}

class PositionedTile extends StatefulWidget {
  const PositionedTile({super.key});

  @override
  State<PositionedTile> createState() => _PositionedTileState();
}

class _PositionedTileState extends State<PositionedTile> {
  late List<Widget> tiles;

  @override
  void initState() {
    super.initState();
    tiles = <StatefullColorTile>[
      StatefullColorTile(),
      StatefullColorTile()
    ];
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Row(
        children: tiles,
      ),
      floatingActionButton: FloatingActionButton(
          onPressed: swapTiles,
          child: const Icon(
            Icons.switch_access_shortcut,
          )),
    );
  }

  void swapTiles() {
    setState(() {
      tiles.insert(1, tiles.removeAt(0));
    });
  }
}

class StatefullColorTile extends StatefulWidget {
  const StatefullColorTile({super.key});

  @override
  State<StatefullColorTile> createState() => _StatelfulColorfulTileState();
}

class _StatelfulColorfulTileState extends State<StatefullColorTile> {
  late Color color;

  @override
  void initState() {
    super.initState();
    color = Colors.primaries[Random().nextInt(Colors.primaries.length)];
  }

  @override
  Widget build(BuildContext context) {
    return Container(width: 100, height: 100, color: color);
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок27.png)<br>
Нужно менять контейнеры местами, они визуально(!) не меняются. Добавим ключи для решения этой проблемы<br>

```
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  runApp(const MaterialApp(
    home: PositionedTile(),
  ));
}

class PositionedTile extends StatefulWidget {
  const PositionedTile({super.key});

  @override
  State<PositionedTile> createState() => _PositionedTileState();
}

class _PositionedTileState extends State<PositionedTile> {
  late List<Widget> tiles;

  // @override
  // void initState() {
  //   super.initState();
  //   tiles = <StatefullColorTile>[
  //     StatefullColorTile(),
  //     StatefullColorTile()
  //   ];
  // }

@override
  void initState() {
    super.initState();
    tiles = [
      StatefullColorTile(
        key: UniqueKey(),
      ),
      StatefullColorTile(
        key: UniqueKey(),
      )
    ];
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Row(
        children: tiles,
      ),
      floatingActionButton: FloatingActionButton(
          onPressed: swapTiles,
          child: const Icon(
            Icons.switch_access_shortcut,
          )),
    );
  }

  void swapTiles() {
    setState(() {
      tiles.insert(1, tiles.removeAt(0));
    });
  }
}

class StatefullColorTile extends StatefulWidget {
  const StatefullColorTile({super.key});

  @override
  State<StatefullColorTile> createState() => _StatelfulColorfulTileState();
}

class _StatelfulColorfulTileState extends State<StatefullColorTile> {
  late Color color;

  @override
  void initState() {
    super.initState();
    color = Colors.primaries[Random().nextInt(Colors.primaries.length)];
  }

  @override
  Widget build(BuildContext context) {
    return Container(width: 100, height: 100, color: color);
  }
}

```

<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок28.png)<br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок29.png)<br>

## _**Лекция 4**_

1.Expanded<br>

```
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  runApp(Container(
    padding: EdgeInsets.only(top:25),
    color: Colors.white,
    child:Row(
        textDirection: TextDirection.ltr,
        crossAxisAlignment: CrossAxisAlignment.start,
        verticalDirection: VerticalDirection.down,
        children: <Widget>[
          Expanded(
              child: Container(color: Colors.primaries[Random().nextInt(Colors.primaries.length)]),
              flex: 3,
          ),
          Expanded(
              child: Container(color: Colors.primaries[Random().nextInt(Colors.primaries.length)]),
              flex:1
          ),
          Expanded(
              child: Container(color: Colors.primaries[Random().nextInt(Colors.primaries.length)]),
              flex: 2,
          )
        ]
      )
    )
  );
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок30.png)<br>

```
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  runApp(Container(
    padding: EdgeInsets.only(top:25),
    color: Colors.white,
    child:Column(//Row
        textDirection: TextDirection.ltr,
        crossAxisAlignment: CrossAxisAlignment.start,
        verticalDirection: VerticalDirection.down,
        children: <Widget>[
          Expanded(
              child: Container(color: Colors.primaries[Random().nextInt(Colors.primaries.length)]),
              flex: 3,
          ),
          Expanded(
              child: Container(color: Colors.primaries[Random().nextInt(Colors.primaries.length)]),
              flex:1
          ),
          Expanded(
              child: Container(color: Colors.primaries[Random().nextInt(Colors.primaries.length)]),
              flex: 2,
          )
        ]
      )
    )
  );
}

```


<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок31.png)<br>

2.Stack<br>

```
import 'dart:math';
import 'package:flutter/material.dart';

void main() {
  runApp(Container(
    color: Colors.white,
    padding: EdgeInsets.only(top:40, bottom: 10, left: 20, right: 20),
    child: Stack(
      textDirection: TextDirection.ltr,
      children: <Widget>[
        Container(
          width: 200,
          height: 200,
          color:  Colors.primaries[Random().nextInt(Colors.primaries.length)],
        ),
        Container(
          width: 160,
          height: 160,
          transform: Matrix4.skewY(0.3)..rotateZ(pi/12),
          color: Colors.primaries[Random().nextInt(Colors.primaries.length)],
        ),
        Container(
          width: 100,
          height: 100,
          decoration: const BoxDecoration(
            border:Border(top: BorderSide(width: 20.0,color: Colors.redAccent)),
            borderRadius: BorderRadius.all( Radius.circular(16)),
            gradient: 
            LinearGradient(
              colors: [ Colors.amber, Colors.greenAccent]
            )
          ),
        ),
      ],
    )
  )
  );
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок32.png)<br>

3.ListView<br>

```
const double textSize = 22;
void main() {
  runApp(MaterialApp(
      home:  Scaffold(
        body: ListView(
          padding: const EdgeInsets.all(8),
          children:[
            Text("Tom", style: TextStyle(fontSize: textSize)),
            Text("Alice", style: TextStyle(fontSize: textSize)),
            Text("Bob", style: TextStyle(fontSize: textSize)),
            Text("Sam", style: TextStyle(fontSize: textSize)),
            Text("Kate", style: TextStyle(fontSize: textSize)),
          ],
        ),
  )));
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок33.png)<br>

```
const double textSize = 22;
void main() {
  runApp(MaterialApp(
      home:  Scaffold(
        body: ListView(
          padding: const EdgeInsets.all(8),
          scrollDirection: Axis.horizontal,
          children:[
            Text("Tom ", style: TextStyle(fontSize: textSize)),
            Text("Alice ", style: TextStyle(fontSize: textSize)),
            Text("Bob ", style: TextStyle(fontSize: textSize)),
            Text("Sam ", style: TextStyle(fontSize: textSize)),
            Text("Kate ", style: TextStyle(fontSize: textSize)),
          ],
        ),
  )));
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок34.png)<br>
  
```
final List<String> users = ["Tom", "Alice", "Sam", "Bob", "Kate"];
void main() {
  runApp(MaterialApp(
      home:  Scaffold(
        body: ListView.separated(
            padding: const EdgeInsets.all(8),
            itemCount: users.length,
            separatorBuilder: (BuildContext context, int index) => Divider(),
            itemBuilder: (BuildContext context, int index) {
              return Container(
                padding: EdgeInsets.symmetric(vertical: 10),
                child: Text(users[index], style: TextStyle(fontSize: 22))
              );
            }
        ),
     )
  ));
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок35.png)<br>

## _**Лекция 5**_
1. Null-aware операторы<br>
```
import 'package:flutter/material.dart';

void main() {
baseExample();
}

const count=5;
void baseExample(){
    print('count = $count');

    var countVar=5.3;
    countVar++;
    print('countVar = ${countVar.runtimeType}');
    print('countVar = ${countVar}');

    final List<int> list = [];
    list.add(1);
    list.add(1);
    print(list);

     int? num1 = 23;
    int num2 = num1 ?? 0;
    print(num2);        // 23
     
    num1 = null;
    num2 = num1 ?? 0;
    print(num2);        // 0

        int? a;
    a = a ?? 10;
    print(a);       // 10

      int i = 0;
    i = getInt()!;
    print(i);
}

int? getInt() {
  return 1;
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок36.png)<br>
2. Каскадный null-aware оператор<br>
```
void main() {
baseExample();
}

void baseExample(){
    Sport sport = Sport()
        ..name = "Football"
        ..players = 11;

    print(sport.name);
    print(sport.players);
    print(sport.runtimeType);
}
class Sport{
  String? name;
  int? players;
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок37.png)<br>

3. Модификатор late<br>
```
void main() {
baseExample();
}

void baseExample(){
    Person tom = Person("Tom");
    tom.setAge(38);
    tom.display();
}
class Person{
    String name;
    late int age;   // отложенная инициализация
 
    Person(this.name);
    void setAge(int age){
 
        if(age > 0 && age < 111) this.age = age;
        else this.age = 18;
    }
    void display() => print("Name: $name \tAge: $age");
}


```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок38.png)<br>
4. Работа с коллекциями<br>
```
import 'dart:async';
import 'package:flutter/material.dart';

void main() {
baseExample();
}

void baseExample(){
List<String>? myColors = ["Blue", "Green", "Red"];
print(myColors[1]);
myColors = null;
String? green = myColors?[1];
print(green);
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок39.png)<br>
5.Работа с параметрами класса<br>
```
void main() {
baseExample();
}

void baseExample(){
    Person tom = Person(134, "Tom");
    print(tom.id);
    Person bob = Person("324", "Bob");
    print(bob.id);

    Person<String> bob1 = Person<String>("324", "Bob");
    print(bob1.id.runtimeType);
    Person<int> sam = Person<int>(123, "Sam");
    print(sam.id.runtimeType);
}

class Person<T>{
    T id;   // идентификатор пользователя
    String name; // имя пользователя
    Person(this.id, this.name);
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок40.png)<br>
## _**Лекция 6**_
1. Простая передача данных между экранами, навигация<br>
```
import 'package:flutter/material.dart';
import 'dart:math';

void main() {
  runApp(MaterialApp(
    routes: {
      '/': (context) => HomeScreen(title: 'Home'), 
      '/second': (context) => SecondScreen(data: 'Hello'), 
    },
  ));
}

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key, required this.title});
  final String title;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text(title)), 
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.pushNamed(context, '/second'); 
          },
          child: Text("Second"),
           style: ButtonStyle(
                backgroundColor: MaterialStateProperty.all(Colors.primaries[Random().nextInt(Colors.primaries.length)],),
                foregroundColor: MaterialStateProperty.all(Colors.black),
                ),
        ),
      ),
    );
  }
}

class SecondScreen extends StatelessWidget {
  final String data;
  SecondScreen({required this.data});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Second Screen')),
      body: Center(child: Text(data)), 
    );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок41.png)<br>
   ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок42.png)<br>
2. Передача данных с onGenerateRoute<br>
```
import 'package:flutter/material.dart';
import 'dart:math';

void main() {
 runApp(MaterialApp(
    onGenerateRoute: (settings) {
      var path = settings.name?.split('/') ?? [];

      if (settings.name == '/') {
        return MaterialPageRoute(builder: (context) {
          return const HomeScreen(title: 'Home');
        });
      }

      if ((path.length >= 3) && path[1] == 'second') {
        return MaterialPageRoute(builder: (context) {
          return SecondScreen(data: path[2]);
        });
      }
      return MaterialPageRoute(builder: (context) {
        return const HomeScreen(title: 'Home');
      });
    },
  ));
}

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key, required this.title});
  final String title;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text(title)), 
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            //Navigator.pushNamed(context, '/second'); 
            Navigator.of(context)
                  .pushNamed('/second/hello');
          },
          child: Text("Second"),
           style: ButtonStyle(
                backgroundColor: MaterialStateProperty.all(Colors.primaries[Random().nextInt(Colors.primaries.length)],),
                foregroundColor: MaterialStateProperty.all(Colors.black),
                ),
        ),
      ),
    );
  }
}

class SecondScreen extends StatelessWidget {
  final String data;
  SecondScreen({required this.data});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Second Screen')),
      body: Center(child: Text(data)), 
    );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок43.png)<br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок42.png)<br>

## _**Лекция 7**_
1. Form, TextField и TextFormField<br>
```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyCustomForm());
}
class MyCustomForm extends StatefulWidget {
  const MyCustomForm({super.key});

  @override
  MyCustomFormState createState() {
    return MyCustomFormState();
  }
}

class MyCustomFormState extends State<MyCustomForm> {
  final _formKey = GlobalKey<FormState>();

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Custom Form'),
        ),
        body: Form(
          key: _formKey,
          child: Padding(
            padding: const EdgeInsets.all(16.0),
            child: Column(
              children: <Widget>[
                TextFormField(
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter some text';
                    }
                    return null;
                  },
                ),
                const SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () {
                    if (_formKey.currentState!.validate()) {
                      ScaffoldMessenger.of(context).showSnackBar(
                        const SnackBar(content: Text('Processing Data')),
                      );
                    }
                  },
                  child: const Text('Submit'),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок44.png)<br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок45.png)<br>
2. Стилизация полей ввода<br>
```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyCustomForm());
}
class MyCustomForm extends StatefulWidget {
  const MyCustomForm({super.key});

  @override
  MyCustomFormState createState() {
    return MyCustomFormState();
  }
}

class MyCustomFormState extends State<MyCustomForm> {
  final _formKey = GlobalKey<FormState>();

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Custom Form'),
        ),
        body: Form(
          key: _formKey,
          child: Padding(
            padding: const EdgeInsets.all(16.0),
            child: Column(
              children: <Widget>[
                TextFormField(
                  decoration: InputDecoration(
            border: InputBorder.none,
            hintText: "Введите логин",
            fillColor: Colors.black12,
            filled: true
        ),
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter some text';
                    }
                    return null;
                  },
                ),
                const SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () {
                    if (_formKey.currentState!.validate()) {
                      ScaffoldMessenger.of(context).showSnackBar(
                        const SnackBar(content: Text('Processing Data')),
                      );
                    }
                  },
                  child: const Text('Submit'),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок46.png)<br>
3. Ограничения ввода в поля формы<br>
```
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';

void main() {
  runApp(const MyCustomForm());
}
class MyCustomForm extends StatefulWidget {
  const MyCustomForm({super.key});

  @override
  MyCustomFormState createState() {
    return MyCustomFormState();
  }
}

class MyCustomFormState extends State<MyCustomForm> {
  final _formKey = GlobalKey<FormState>();

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Custom Form'),
        ),
        body: Form(
          key: _formKey,
          child: Padding(
            padding: const EdgeInsets.all(16.0),
            child: Column(
              children: <Widget>[
                TextFormField(
                  decoration: InputDecoration(
            border: InputBorder.none,
            hintText: "Введите логин",
            fillColor: Colors.black12,
            filled: true
        ),
                  validator: (value) {
                    if (value == null || value.isEmpty) {
                      return 'Please enter some text';
                    }
                    return null;
                  },
                     inputFormatters: [
              FilteringTextInputFormatter.allow(RegExp(r'[0-9]')),
              FilteringTextInputFormatter.deny(RegExp(r'1')),
              LengthLimitingTextInputFormatter(4)
            ],
                ),
                const SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () {
                    if (_formKey.currentState!.validate()) {
                      ScaffoldMessenger.of(context).showSnackBar(
                        const SnackBar(content: Text('Processing Data')),
                      );
                    }
                  },
                  child: const Text('Submit'),
                ),
              ],
            ),
          ),
        ),
      ),
    );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок47.png)<br>
4. Получение текста из полей формы<br>
```
import 'package:flutter/material.dart';
 
void main() {
  runApp(MaterialApp(
      home:  Scaffold(
        body: Person(),
       )
  ));
}
 
class Person extends StatefulWidget {
  Person({super.key});
  //Person({ Key key}) : super(key: key);
 
  @override
  _PersonState createState() => _PersonState();
}
class _PersonState extends State<Person>{
 
  String _name = "Tom";
  final _controller = TextEditingController();
 
  _changeName(){
    setState(() =>_name = _controller.text);
  }
 
  @override
  void initState() {
    super.initState();
    _controller.text = _name;
    _controller.addListener(_changeName);
  }
  @override
  void dispose() {
    _controller.dispose();
    super.dispose();
  }
  @override
  Widget build(BuildContext context) {
 
    return Column(children:[
      Text("Имя пользователя: $_name", style: TextStyle(fontSize: 22)),
      TextField(
          style: TextStyle(fontSize: 22),
          controller: _controller)
    ],
    crossAxisAlignment: CrossAxisAlignment.start);
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок48.png)<br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок49.png)<br>
5.  Выпадающий список<br>
```
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Dropdown',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Dropdown'),
        ),
        body: Center(child: DropdownItem(),),
      ),
    );
  }
}

class DropdownItem extends StatefulWidget {
  @override
  _DropdownItemState createState() => _DropdownItemState();
}

class _DropdownItemState extends State<DropdownItem> {
  String selectedValue = "USA";

  List<DropdownMenuItem<String>> get dropdownItems{
  List<DropdownMenuItem<String>> menuItems = [
    DropdownMenuItem(child: Text("USA"),value: "USA"),
    DropdownMenuItem(child: Text("Canada"),value: "Canada"),
    DropdownMenuItem(child: Text("Brazil"),value: "Brazil"),
    DropdownMenuItem(child: Text("England"),value: "England"),
  ];
  return menuItems;
}

  @override
  Widget build(BuildContext context) {
    return DropdownButton(
      value: selectedValue,
      onChanged: (String? newValue){
        setState(() {
          selectedValue = newValue!;
        });
      },
      items: dropdownItems
      );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок50.png)<br>

6. "Фокусировка" полей ввода<br>
```
import 'package:flutter/material.dart';

void main() {
    runApp(MaterialApp(
      home:  Scaffold(
        body: MyCustomForm(),
       )
  ));

}

// Define a custom Form widget.
class MyCustomForm extends StatefulWidget {
  const MyCustomForm({super.key});

  @override
  State<MyCustomForm> createState() => _MyCustomFormState();
}

// Define a corresponding State class.
// This class holds data related to the form.
class _MyCustomFormState extends State<MyCustomForm> {
  // Define the focus node. To manage the lifecycle, create the FocusNode in
  // the initState method, and clean it up in the dispose method.
  late FocusNode myFocusNode;

  @override
  void initState() {
    super.initState();

    myFocusNode = FocusNode();
  }

  @override
  void dispose() {
    // Clean up the focus node when the Form is disposed.
    myFocusNode.dispose();

    super.dispose();
  }

  @override
   Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: TextField(
          focusNode: myFocusNode,
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () => myFocusNode.requestFocus(),
      ),
    );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок51.png)<br>
7. SnackBar<br>
```
import 'package:flutter/material.dart';

void main() {
    runApp(MaterialApp(
  title: 'SnackBar Demo',
  home: Scaffold(
    appBar: AppBar(
      title: const Text('SnackBar Demo'),
    ),
    body: const MyCustomForm(),//SnackBarPage
  )
  )
    );
}

// Define a custom Form widget.
class MyCustomForm extends StatefulWidget {
  const MyCustomForm({super.key});

  @override
  State<MyCustomForm> createState() => _MyCustomFormState();
}

class _MyCustomFormState extends State<MyCustomForm> {
  @override
  void initState() {
    super.initState();
  }

   void _showSnackBar() {
    final snackBar = SnackBar(
      content: const Text('Yay! A SnackBar!'),
    );

    // Показываем SnackBar
    ScaffoldMessenger.of(context).showSnackBar(snackBar);
  }

  @override
   Widget build(BuildContext context) {
    return Scaffold(
     // body: Center(),
      floatingActionButton: FloatingActionButton(
        onPressed: () => _showSnackBar(),
        child: Text("Show"),
      ),
      );
  }
}

```
<br>

  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок52.png)<br>
  ![Dow](https://github.com/Pomelogranate/Flutter/blob/main/images/Рисунок53.png)<br>
