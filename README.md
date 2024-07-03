# rn-assignment6-11356857

This is a React Native application for a fashion store that allows users to browse products, add them to a cart, and proceed to checkout. The app features a home screen displaying a list of products and a cart screen where users can view and manage items in their cart.

## Features
- Home Screen: Browse a list of fashion products with images, descriptions, and prices. Users can add products to their cart.
- Cart Screen: View items added to the cart, remove items, and see the total price. Users can proceed to checkout.
- Data Persistence: The cart data is stored using AsyncStorage, ensuring that the cart contents persist across app restarts.
- Navigation: The app uses React Navigation for smooth transitions between the home and cart screens.
  
## Installation
Clone the repository:

``sh
https://github.com/schooltech1/rn-assignment6-11356857.git
cd my-app
``

Install the dependencies:

``sh
npm install
``


Run the app:

``sh
npx react-native run-android # For Android
npx react-native run-ios # For iOS
``
## Screens and Components
- HomeScreen.js
  - Displays a list of products.
  - Users can add products to their cart.
  - Uses a FlatList for efficient rendering of product items.
  - Stores the cart data using AsyncStorage.
    
- CheckOutScreen.js
 - Displays items added to the cart.
 - Users can remove items from the cart.
 - Shows the total price of the items in the cart.
 - Uses a FlatList for efficient rendering of cart items.
 - Calculates the total price dynamically based on cart contents.
   
- Header.js
 - Custom header component with a logo and search icon.
 - Displays a checkout text with an underline for visual separation.
   
- OpenFashionUI.js
 - UI component for displaying the top navigation with menu, logo, and search icons.
 - Includes a section for "Our Story" with additional icons for filter and list view.
   
- Data Storage
The app uses AsyncStorage for data persistence, ensuring that the cart contents are saved and loaded across app sessions. This is implemented in both the HomeScreen and CheckOutScreen components. When a user adds or removes an item from the cart, the updated cart is saved to AsyncStorage.

## Adding Items to Cart
- In HomeScreen.js:
``
const addToCart = async (product) => {
  const updatedCart = [...cart, product];
  setCart(updatedCart);
  await AsyncStorage.setItem('cart', JSON.stringify(updatedCart));
};``
## Removing Items from Cart
- In CheckOutScreen.js:
``
const removeFromCart = async (productId) => {
  const updatedCart = cart.filter((item) => item.id !== productId);
  setCart(updatedCart);
  await AsyncStorage.setItem('cart', JSON.stringify(updatedCart));
  calculateTotal(updatedCart);
};``
## Design Choices
- Responsive Design: The app is designed to be responsive, adjusting image sizes and layouts based on the device's screen width.
  
- FlatList: Used for efficient rendering of product and cart items, providing a smooth user experience even with a large number of items.
  
- Navigation: React Navigation is used for managing navigation between the home and cart screens, providing a clean and intuitive user flow.
  
- AsyncStorage: Chosen for its simplicity and effectiveness in storing key-value pairs, ensuring data persistence without the need for a more complex database solution.




## Screen Recording
https://github.com/schooltech1/rn-assignment6-11356857/assets/170237696/cb5273b3-a9a8-4b46-aa42-23592b5f6d54
