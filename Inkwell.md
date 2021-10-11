-import 'dart:math';

import 'package:flutter/cupertino.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(Appmah());
}

class Appmah extends StatefulWidget {
  @override
  _AppmahState createState() => _AppmahState();
}

class _AppmahState extends State<Appmah> {
  bool Like = false;
  bool comment = false;
  bool share = false;

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        debugShowCheckedModeBanner: false,
        home: Scaffold(
            appBar: AppBar(
              leading: Icon(Icons.add_shopping_cart),
              backgroundColor: Colors.green,
              title: Text('myapp'),
              actions: [
                IconButton(
                    onPressed: () {
                      print('hello');
                    },
                    icon: Icon(Icons.add_a_photo_outlined))
              ],
            ),
            body: Center(
              child: Container(
                height: 700,
                width: 400,
                padding: EdgeInsets.all(5),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    ListTile(
                      leading: CircleAvatar(
                        radius: 40,
                        backgroundImage: NetworkImage(
                            'data:image/jpeg;base64,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'),
                      ),
                      title: Text(
                        'التراس حاسبات ومعلومات',
                        style: TextStyle(fontWeight: FontWeight.bold),
                      ),
                      subtitle: Text('17H'),
                      trailing: IconButton(
                        onPressed: () {},
                        icon: Icon(
                          Icons.more_horiz_rounded,
                        ),
                      ),
                    ),
                    SizedBox(
                      height: 10,
                    ),
                    Text('Linkedin'),
                    SizedBox(height: 10,),
                    Column(
                      crossAxisAlignment: CrossAxisAlignment.center,
                      mainAxisAlignment: MainAxisAlignment.center,
                      children: [
                        Image.asset('assets/Images/245079714_2429313067200726_4831149910419777166_n.jpg'),
                      ],
                    ),
                    SizedBox(
                      height: 10,
                    ),
                    Row(mainAxisAlignment:MainAxisAlignment.spaceAround ,
                      children: [
                      Text('981 Like'),
                      Text('31 Comments'),
                      Text('130 Shares'),
                    ],),
                    SizedBox(height: 5,),
                    Divider(
                      color: Colors.black,
                    ),
                    Row(mainAxisAlignment: MainAxisAlignment.spaceAround,
                      children: [
                        InkWell(
                          onTap: () {
                            setState(() {
                              Like = !Like;
                            });
                          },
                          child: Like
                              ?Icon(
                            Icons.thumb_up,
                            color: Colors.blue,
                          ): Icon(
                                  Icons.thumb_up_alt_outlined,
                                ),

                        ),
                        InkWell(
                          onTap: (){
                            setState(() {
                              comment=!comment;
                            });
                          },
                          child: comment? Icon(Icons.comment,color: Colors.amber,):Icon(Icons.comment),
                        ),
                        InkWell(
                          onTap: (){
                            setState(() {
                              share=!share;
                            });
                          },
                          child: share?Icon(Icons.forward_outlined,color: Colors.pink,):Icon(Icons.forward_outlined),
                        )
                      ],
                    ),
                  ],
                ),
              ),
            )));
  }
}
