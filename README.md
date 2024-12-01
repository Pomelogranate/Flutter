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
          color:  Colors.primaries[Random().nextInt(Colors.primaries.length)],
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






















  
