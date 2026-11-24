
```
import 'package:flutter/material.dart';
import 'dart:convert';
import 'package:http/http.dart' as http;
import 'package:network_db/networksimplepage.dart';

void main() {
  runApp( MyApp());

}


class MyApp extends StatelessWidget{

  MyApp({super.key});

  @override
  Widget build(BuildContext context){
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: "Network + db",
      home: NetworkSimplePage(),
    );


  }

}



```




```
import 'dart:convert';

import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;

class NetworkSimplePage extends StatefulWidget {
  const NetworkSimplePage({super.key});

  @override
  State<NetworkSimplePage> createState() => _NetworkSimplePageState();
}

class _NetworkSimplePageState extends State<NetworkSimplePage> {

  String getTitleOfApi = '';

  @override
  void initState(){
    super.initState();
    getData();

  }

  Future<void> getData() async{
    final url = Uri.parse('https://jsonplaceholder.typicode.com/todos/1');
    final response = await http.get(url);

    if (response.statusCode == 200){
      final data = jsonDecode(response.body);
      setState(() {
        getTitleOfApi = data['title'];
      });
    }
    else {
      setState(() {
        getTitleOfApi = 'Error: ${response.statusCode}';
      });
    }
  }


  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Networking - Paso 1'),
      ),
      body: Center(
        child: Padding(
          padding: const EdgeInsets.all(16),
          child: Text(
            getTitleOfApi,
            style: const TextStyle(fontSize: 18),
            textAlign: TextAlign.center,
          ),
        ),
      ),
    );
  }
}


```
