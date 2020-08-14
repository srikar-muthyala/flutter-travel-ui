class Hotel{
  String imageUrl;
  String name;
  String address;
  int price;

  Hotel({
    this.price,
    this.name,
    this.imageUrl,
    this.address,
  });
}

final List<Hotel> hotels = [
  Hotel(
    imageUrl: 'assets/images/hotel0.jpg',
    name: 'Hotel 0',
    address: '404 Great Av.',
    price: 175,
  ),
  Hotel(
    imageUrl: 'assets/images/hotel1.jpg',
    name: 'Hotel 1',
    address: '405 Great Av.',
    price: 275,
  ),
  Hotel(
    imageUrl: 'assets/images/hotel2.jpg',
    name: 'Hotel 2',
    address: '405 Great Av.',
    price: 225,
  ),
];
