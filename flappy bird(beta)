import 'dart:async';

import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: ' ',
      theme: ThemeData(

        primarySwatch: Colors.blue,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);
  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  static double birdyaxis=0;
  double time=0;
  double height=0;
  double initialheight=birdyaxis;
  bool gamehasstarted=false;

  void jump() {
    setState(() {
      time=0;
      initialheight=birdyaxis;
    });
  }
  void startgame(){
    gamehasstarted=true;
    Timer.periodic(Duration(milliseconds:50), (timer) {
      time+=0.05;
      height=-4.5*time*time+2.8*time;
      setState(() {
        birdyaxis=initialheight-height;
      }
      );
      if(birdyaxis>0){
        timer.cancel();
        gamehasstarted=false;
      }
    });
  }
  void start(){
    gamehasstarted=true;
    Timer.periodic(Duration(milliseconds:50), (timer) {
      time+=0.05;
      height=-4.5*time*time+2.8*time;
      setState(() {
        birdyaxis=initialheight-height;
      }
      );
      if(birdyaxis>1){
        timer.cancel();
        gamehasstarted=false;
      }
    });
  }


  @override
  Widget build(BuildContext context) {

    return Scaffold(
      body:Column(
        children: [

          Expanded(
            flex:2,
            child: GestureDetector(
              onTap: (){
                if(gamehasstarted){
                  jump;

                }
                else{
                  startgame();
                }
              },
            child: AnimatedContainer(
              alignment: Alignment(0,birdyaxis),
              duration: Duration(milliseconds: 0),
              color:Colors.blue,
            child:  Image(
                image: NetworkImage("https://th.bing.com/th/id/R.f7c53cf05f197c71dd8e55d396add0db?rik=C31CROt57PteMA&riu=http%3a%2f%2fwww.pngmart.com%2ffiles%2f12%2fFlappy-Bird-Transparent-Background.png&ehk=oNugMHtMOR2UQf1O2h9b%2bzRDJGpdKrzexB9AYrf08Bc%3d&risl=&pid=ImgRaw&r=0"),
                height:60,
                width:60,
              ),

            ),
          ),
          ),
          Expanded(
            child: Container(color:Colors.green,
            ),
          ),
        ],

      ),
    );
  }
}
