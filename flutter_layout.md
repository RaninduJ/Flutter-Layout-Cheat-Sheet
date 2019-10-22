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

Aligning widgets.
You control how a row or column aligns its children using the mainAxisAlignment and crossAxisAlignment properties. For a row, the main axis runs horizontally and the cross axis runs vertically. For a column, the main axis runs vertically and the cross axis runs horizontally.

Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('images/pic1.jpg'),
    Image.asset('images/pic2.jpg'),
    Image.asset('images/pic3.jpg'),
  ],
);

Columns work the same way as rows. The following example shows a column of 3 images, each is 100 pixels high. The height of the render box (in this case, the entire screen) is more than 300 pixels, so setting the main axis alignment to spaceEvenly divides the free vertical space evenly between, above, and below each image.

Column(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('images/pic1.jpg'),
    Image.asset('images/pic2.jpg'),
    Image.asset('images/pic3.jpg'),
  ],
);

Sizing widgets

When a layout is too large to fit a device, a yellow and black striped pattern appears along the affected edge. Here is an example of a row that is too wide.
Widgets can be sized to fit within a row or column by using the Expanded widget. To fix the previous example where the row of images is too wide for its render box, wrap each image with an Expanded widget.

Row(
  crossAxisAlignment: CrossAxisAlignment.center,
  children: [
    Expanded(
      child: Image.asset('images/pic1.jpg'),
    ),
    Expanded(
      child: Image.asset('images/pic2.jpg'),
    ),
    Expanded(
      child: Image.asset('images/pic3.jpg'),
    ),
  ],
);

Packing widgets
By default, a row or column occupies as much space along its main axis as possible, but if you want to pack the children closely together, set its mainAxisSize to MainAxisSize.min. The following example uses this property to pack the star icons together.

Row(
  mainAxisSize: MainAxisSize.min,
  children: [
    Icon(Icons.star, color: Colors.green[500]),
    Icon(Icons.star, color: Colors.green[500]),
    Icon(Icons.star, color: Colors.green[500]),
    Icon(Icons.star, color: Colors.black),
    Icon(Icons.star, color: Colors.black),
  ],
)

