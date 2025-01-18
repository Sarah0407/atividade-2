git init
git remote add origin https://github.com/seu-usuario/seu-repositorio.git
git add .
git commit -m "Primeiro commit do projeto Flutter"
git push -u origin master

import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Layout Responsivo Flutter'),
        ),
        body: ResponsiveLayout(),
      ),
    );
  }
}

class ResponsiveLayout extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    double width = MediaQuery.of(context).size.width;

    if (width > 600) {
      // Layout para telas grandes (ex: tablets ou desktops)
      return Row(
        children: [
          Expanded(child: Container(color: Colors.blue, height: 200)),
          Expanded(child: Container(color: Colors.green, height: 200)),
        ],
      );
    } else {
      // Layout para telas pequenas (ex: smartphones)
      return Column(
        children: [
          Container(color: Colors.blue, height: 200),
          Container(color: Colors.green, height: 200),
        ],
      );
    }
  }
}
