Add the layout widget to the page

This provides a default banner, background color, and has API for adding drawers, snack bars, and bottom sheets.
Then you can add the Center widget directly to the body property for the page.This is mostly using in MaterialApp.This code is show how to do it.

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter layout demo',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Flutter layout demo'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}

For a non-Material app, you can add it follow this code.By default a non-Material app doesn’t include an AppBar, title, or background color. If you want these features in a non-Material app, you have to build them yourself.
This app changes the background color to white and the text to dark grey to mimic a Material app.

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      decoration: BoxDecoration(color: Colors.white),
      child: Center(
        child: Text(
          'Hello World',
          textDirection: TextDirection.ltr,
          style: TextStyle(
            fontSize: 32,
            color: Colors.black87,
          ),
        ),
      ),
    );
  }
}

create an image widget.

Image.asset(
  'images/lake.jpg',
  fit: BoxFit.cover,
),

create an icon widget.

Icon(
  Icons.star,
  color: Colors.red[100],
),

Add the visible widget to the layout.
A child property if they take a single child – for example, Center or Container
A children property if they take a list of widgets – for example, Row, Column, ListView, or Stack.

Center(
  child: Text('Hello World'),
),