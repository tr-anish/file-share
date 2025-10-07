Something Important


import 'package:flutter/material.dart';

void main() {
  runApp(const MyTabApp());
}

class MyTabApp extends StatelessWidget {
  const MyTabApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Custom TabBar Example',
      theme: ThemeData(primarySwatch: Colors.blue),
      home: const TabBarDemo(),
      debugShowCheckedModeBanner: false,
    );
  }
}

class TabBarDemo extends StatelessWidget {
  const TabBarDemo({super.key});

  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
      length: 3,
      child: Scaffold(
        appBar: AppBar(
          title: const Text('TabBar Example'),
          bottom: PreferredSize(
            preferredSize: const Size.fromHeight(50),
            child: Container(
              margin: const EdgeInsets.all(8),
              decoration: BoxDecoration(
                color: Colors.white,
                border: Border.all(color: Colors.blue, width: 1.5),
                borderRadius: BorderRadius.circular(10),
              ),
              child: TabBar(
                labelColor: Colors.white,
                unselectedLabelColor: Colors.blue,
                indicator: BoxDecoration(
                  color: Colors.blue,
                  borderRadius: BorderRadius.circular(8),
                ),
                tabs: const [
                  Tab(text: "Scheme Wise"),
                  Tab(text: "Type Wise"),
                  Tab(text: "SubType Wise"),
                ],
              ),
            ),
          ),
        ),
        body: const TabBarView(
          children: [
            Center(child: Text("Scheme Wise Content")),
            Center(child: Text("Type Wise Content")),
            Center(child: Text("SubType Wise Content")),
          ],
        ),
      ),
    );
  }
}