# syntex

```dart
//State notifier
final progressInt = StateNotifierProvider<ProgressIntNotifier, int>((ref) => ProgressIntNotifier());

class ProgressIntNotifier extends StateNotifier<int> {
  ProgressIntNotifier() : super(16);
  set value(int text) =>
      state = text; // value and text are just name can be any word , ///state can be used directly in place of value in comment dialog
}
  
  
//Async Notifier Family /Equitable
  
  Scaffold(
      body: ref.watch(provider(ddd)).when(
          data: (List<Commett> a) => ListView.builder(
              cacheExtent: 88888,
              itemCount: a.length,
              itemBuilder: (context, index) {
                return Center(
                  child: Text(
                     a[index].title,
                  ),
                );
              }),
          error: (error, stack) => Text(error.toString()),
          loading: () => const Center(child: CircularProgressIndicator())),
  
  
final provider = AsyncNotifierProviderFamily<MyNotifier, List<Commett>, Commett>(MyNotifier.new);
class MyNotifier extends FamilyAsyncNotifier<List<Commett>, Commett> {
  List<Commett> comments = [];
  @override
  Future<List<Commett>> build(arg) async {
    // List<Comment> comments;
    DateTime x = DateTime.now();
    Commett c = Commett(title: 'tt', text: 'tt', createdAt: x, id: '11');
    Commett d = Commett(title: 'ff', text: 'ff', createdAt: x, id: '11');
    List<Commett> m = [c, d];
    List<Commett> n = [d, d];
    Commett xta = arg;
    n.add(xta);
    print(xta);
    return n;
  }

  doSomething() async {
    update((data) async {
      state = const AsyncLoading();
      await Future.delayed(const Duration(seconds: 1));
      print(comments);
      return comments;
    });
  }
}
//Createdclass using quicktype.io  website then added Equitable
//without equitable build was called repeatedly

Commett commettFromJson(String str) => Commett.fromJson(json.decode(str));

String commettToJson(Commett data) => json.encode(data.toJson());

class Commett extends Equatable {
  String id;
  String title;
  String text;
  DateTime createdAt;

  Commett({
    required this.id,
    required this.title,
    required this.text,
    required this.createdAt,
  });

  factory Commett.fromJson(Map<String, dynamic> json) => Commett(
        id: json["id"],
        title: json["title"],
        text: json["text"],
        createdAt: DateTime.parse(json["createdAt"]),
      );

  Map<String, dynamic> toJson() => {
        "id": id,
        "title": title,
        "text": text,
        "createdAt": createdAt.toIso8601String(),
      };

  @override
  // TODO: implement props
  List<Object> get props => [id];
  // List<Object> get props => [title];
  // List<Object> get props => [text];
  // List<Object> get props => [createdAt];
  // List<Object?> get props => throw UnimplementedError();
}
```
---  

  ```dart
  #Responce from Api
  final response = await http.post(Uri.parse('https://reqres.in/api/users?delay=3'),
      headers: {
        // 'Content-type': 'application/json; charset=UTF-8',
      },
      body: {
        "email": "eve.holt@reqres.in",
        "password": "pistol"
      },
    );
  
 ``` 
  
  #### Custom Painter
  ```dart
//in Build
  child: CustomPaint(
              size: Size(MediaQuery.of(context).size.width / 9, size.height*.022),
              painter: RPSCustomPainter(),
            ),
 
class RPSCustomPainter extends CustomPainter{
  @override
  void paint(Canvas canvas, Size size) {
  
    Paint paint0 = Paint()
      ..color = Colors.white
      ..style = PaintingStyle.fill
      ..strokeWidth = 1;
  
    Path path0 = Path();
    path0.moveTo(0,0);
    path0.quadraticBezierTo(size.width*0.7500000,0,size.width,0);
    path0.quadraticBezierTo(size.width*0.9844000,size.height*0.1986000,size.width*0.8810000,size.height*0.2000000);
    path0.cubicTo(size.width*0.8224000,size.height*0.2037000,size.width*0.5656000,size.height*0.2001000,size.width*0.6019000,size.height*0.1995000);
    path0.close();

    canvas.drawPath(path0, paint0);

  }

  @override
  bool shouldRepaint(covariant CustomPainter oldDelegate) {
    return true;
  }

}
```
---

  #### Completer

  ```dart

        
        final done = Completer<void>();
  runApp(MyApp4(done:done ,));
       
        
 class MyApp4 extends StatefulWidget {
  const MyApp4({required this.done,Key? key}) : super(key: key);
        
 final Completer<void> done;

  @override
  State<MyApp4> createState() => _MyApp4State();
}
class _MyApp4State extends State<MyApp4> {
  @override
  void initState() {
    super.initState();
    timerfunction();
  }
  @override
  Widget build(BuildContext context) {
    return MaterialApp(home: Splash()
    );
  }
  timerfunction(){
    Timer(Duration(seconds: 2), () =>widget.done.complete());
  }
}
```

  // Container(color: Colors.primaries[ index % Colors.primaries.length],),
