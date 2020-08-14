import 'package:flutter/material.dart';
import 'package:flutter_ui_travel/widgets/destination_carousel.dart';
import 'package:flutter_ui_travel/widgets/hotel_carousel.dart';
import 'package:font_awesome_flutter/font_awesome_flutter.dart';

class HomeScreen extends StatefulWidget {
  @override
  _HomeScreenState createState() => _HomeScreenState();
}

class _HomeScreenState extends State<HomeScreen> {

  int _selectedIndex = 0;
  int _currentTab = 0;

  List<IconData> _icons = [
    FontAwesomeIcons.plane,
    FontAwesomeIcons.bed,
    FontAwesomeIcons.walking,
    FontAwesomeIcons.biking,
  ];

  Widget _buildIcon(int index) {
    return GestureDetector(
      onTap: (){
        setState(() {
          _selectedIndex = index;
        });
      },
      child: Container(
        height: 60.0,
        width: 60.0,
        decoration: BoxDecoration(
          color: _selectedIndex == index ? Theme.of(context).accentColor : Color(0xffe7ebee),
          borderRadius: BorderRadius.circular(30.0),
        ),
        child: Icon(
            _icons[index],
            size: 25.0,
            color: _selectedIndex == index ? Theme.of(context).primaryColor : Color(0xffb4c1c4)),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: SafeArea(
        child: ListView(
            padding: EdgeInsets.symmetric(vertical: 30.0),
            children: <Widget>[
                  Padding(
                      padding: const EdgeInsets.only(left: 20.0, right: 120.0),
                      child: Text('What would you like to find?',
                        style: TextStyle(
                        fontSize: 30.0, fontWeight: FontWeight.bold
                    ),
                  ),
                ),
                SizedBox(height: 20.0),
                Row(
                  mainAxisAlignment: MainAxisAlignment.spaceAround,
                  children: _icons.
                  asMap().
                  entries.
                  map((MapEntry map) => _buildIcon(map.key),
                  ).toList(),
                ),
              SizedBox(height: 20.0),
              DestinationCarousel(),
              SizedBox(height: 20.0),
              HotelCarousel(),
          ],
        ),
      ),
      bottomNavigationBar: BottomNavigationBar(
        currentIndex: _currentTab,
        onTap: (int value){
          setState(() {
            _currentTab = value;
          });
        },
        items: [
          BottomNavigationBarItem(icon: Icon(
            Icons.search,
            size: 30.0,
            ),
            title: SizedBox.shrink(),
          ),
          BottomNavigationBarItem(icon: Icon(
            Icons.local_pizza,
            size: 30.0,
            ),
            title: SizedBox.shrink(),
          ),
          BottomNavigationBarItem(icon: CircleAvatar(radius: 15.0, backgroundImage: NetworkImage('data:image/jpeg;base64,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'),),
            title: SizedBox.shrink(),
          ),
        ],


      ),
    );
  }

}