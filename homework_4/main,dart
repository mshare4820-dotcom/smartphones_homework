import 'package:flutter/material.dart';

void main() => runApp(MaterialApp(home: MyHomePage()));

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  final List<String> brands = ["Apple", "Google", "Samsung", "Sony"];
  String selectedBrand = "Apple";

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text("Product Listing")),
      body: Column(
        children: [
          Padding(
            padding: const EdgeInsets.all(16.0),
            child: Row(
              mainAxisAlignment: MainAxisAlignment.spaceBetween,
              children: [
                Text("الماركة:", style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold)),
                DropdownButton<String>(
                  value: selectedBrand,
                  items: brands.map((String value) {
                    return DropdownMenuItem<String>(
                      value: value,
                      child: Text(value),
                    );
                  }).toList(),
                  onChanged: (newValue) {
                    setState(() {
                      selectedBrand = newValue!;
                    });
                  },
                ),
              ],
            ),
          ),
          Expanded(
            child: ListView(
              padding: const EdgeInsets.fromLTRB(2.0, 10.0, 2.0, 10.0),
              children: <Widget>[
                ProductBox(
                    name: "iPhone",
                    brand: selectedBrand,
                    description: "iPhone is the stylish phone ever",
                    price: 1000,
                    image: "https://picsum.photos/id/160/200"),
                ProductBox(
                    name: "Pixel",
                    brand: selectedBrand,
                    description: "Pixel is the most featureful phone ever",
                    price: 800,
                    image: "https://picsum.photos/id/1/200"),
                ProductBox(
                    name: "Laptop",
                    brand: selectedBrand,
                    description: "Laptop is most productive development tool",
                    price: 2000,
                    image: "https://picsum.photos/id/0/200"),
              ],
            ),
          ),
        ],
      ),
    );
  }
}

class ProductBox extends StatelessWidget {
  ProductBox({required this.name, required this.description, required this.price, required this.image, required this.brand});

  final String name;
  final String description;
  final int price;
  final String image;
  final String brand;

  @override
  Widget build(BuildContext context) {
    return Container(
        padding: EdgeInsets.all(2),
        height: 140,
        child: Card(
            child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                children: <Widget>[
              Image.network(image, width: 100),
              Expanded(
                  child: Container(
                      padding: EdgeInsets.all(5),
                      child: Column(
                        mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                        children: <Widget>[
                          Text(this.name, style: TextStyle(fontWeight: FontWeight.bold)),
                          Text("Brand: " + this.brand, style: TextStyle(color: Colors.blue, fontWeight: FontWeight.bold)),
                          Text(this.description),
                          Text("Price: " + this.price.toString()),
                        ],
                      )))
            ])));
  }
}
