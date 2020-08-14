import 'package:flutter/material.dart';
import 'home_screen.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      theme: ThemeData(
        primaryColor: Color(0xff3CBACE),
        accentColor: Color(0xffd8ecf1),
        scaffoldBackgroundColor: Color(0xffF3F5F7),
      ),
      home: HomeScreen(),
    );
  }
}
