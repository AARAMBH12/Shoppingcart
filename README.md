# React Shopping Cart

A modern, fully functional shopping cart application built with React 19, Material-UI (MUI), and TypeScript. The app fetches real products from the FakeStoreAPI and allows users to browse, add items to cart, and manage quantities.

## 🎯 Features

- **Product Browsing**: Fetch and display products from FakeStoreAPI
- **Add to Cart**: Add items to shopping cart with a single click
- **Quantity Management**: Increase or decrease item quantities in the cart
- **Cart Drawer**: Side drawer displaying all cart items with real-time totals
- **Responsive Grid Layout**: Mobile-friendly design that adapts to different screen sizes (1 column on mobile, 3 columns on desktop)
- **Cart Badge**: Display total number of items in the cart
- **Loading States**: Progress indicator while fetching products
- **Error Handling**: Graceful error messages if data fetch fails
- **Type-Safe**: Full TypeScript support for better code reliability

## 📋 Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)

## 🚀 Getting Started

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd react-shopping-cart
```

2. Install dependencies:

```bash
npm install
```

### Running the Application

**Development Mode:**

```bash
npm start
```

Opens the app at [http://localhost:3000](http://localhost:3000). The page automatically reloads when you make changes.

**Production Build:**

```bash
npm run build
```

Creates an optimized production build in the `build` folder, ready for deployment.

## 📁 Project Structure

```
src/
├── App.tsx                 # Main app component with cart logic
├── App.styles.ts          # Styled components for App
├── index.tsx              # React 19 entry point with createRoot
├── Item/
│   ├── Item.tsx           # Product item component
│   └── Item.styles.ts     # Item card styles
├── Cart/
│   ├── Cart.tsx           # Cart container component
│   └── Cart.styles.ts     # Cart aside styles
├── CartItem/
│   ├── CartItem.tsx       # Individual cart item component
│   └── CartItem.styles.ts # CartItem styles
└── index.css              # Global styles
```

## 🛠️ Technologies Used

- **React 19.2.4** - Latest UI framework with new APIs
- **TypeScript 4.9.5** - Type-safe JavaScript
- **Material-UI (MUI) 7.3.9** - Modern component library
  - Drawer - Side navigation for cart
  - Button - Interactive buttons
  - Badge - Cart item count display
  - LinearProgress - Loading indicator
  - Box - Layout container
- **@mui/icons-material 7.3.9** - Icon library (AddShoppingCart icon)
- **Styled Components 6.3.12** - CSS-in-JS styling
- **React Scripts 5.0.1** - Build and development tools
- **FakeStoreAPI** - Product data source

## 💻 How to Use

1. **Browse Products**: The app automatically loads products from FakeStoreAPI on startup
2. **Add to Cart**: Click the "Add to cart" button on any product card
3. **View Cart**: Click the shopping cart badge icon (top-right corner) to open the cart drawer
4. **Adjust Quantities**:
   - Click the **+** button to increase item quantity
   - Click the **-** button to decrease quantity or remove the item
5. **View Total**: The total price is calculated automatically and displayed at the bottom of the cart
6. **Close Cart**: Click outside the drawer or click the icon again to close

## 🔄 Data Flow Architecture

```
FakeStoreAPI
      ↓
useEffect (fetch on mount)
      ↓
App.tsx (state management)
      ↓
handleAddToCart / handleRemoveFromCart
      ↓
Item Component ← → Cart Drawer ← → CartItem Component
```

### State Management

- **cartItems**: Array of items currently in the cart
- **data**: Products fetched from API
- **cartOpen**: Boolean for drawer visibility
- **isLoading**: Loading state while fetching products
- **error**: Error flag if API call fails

## 📦 Available Scripts

### `npm start`

Runs the app in development mode with hot reloading

### `npm run build`

Creates a production-ready build (119.6 kB gzipped)

### `npm test`

Runs the test runner in interactive watch mode

### `npm run eject`

⚠️ One-way operation - ejects from Create React App (not recommended)

## 🎨 Component Details

### App.tsx

- Main component managing all state and logic
- Fetches products using `useEffect` hook
- Implements add/remove cart functionality
- Renders responsive grid layout using MUI Box
- Displays loading progress and error states

### Item.tsx

- Displays individual product card
- Shows product image, title, description, and price
- "Add to cart" button triggers cart update
- Styled with custom CSS-in-JS

### Cart.tsx

- Container component for cart drawer
- Maps through cartItems and renders CartItem components
- Calculates and displays total price
- Shows "No items in cart" message when empty

### CartItem.tsx

- Shows each item in the cart with details
- Quantity adjustment buttons (+/-)
- Displays item price and total for that item
- Product image and title

## 🎨 Styling

The app uses **styled-components** for CSS-in-JS styling combined with MUI's component system:

- Responsive grid: `display: grid` with responsive columns
- Fixed cart button: `position: fixed` in top-right corner
- Drawer container: Fixed width with padding

## 🚀 Deployment

After running `npm run build`, the `build` folder is ready for deployment:

**Netlify**: Drag and drop the `build` folder
**Vercel**: Connect your repo, it auto-detects React
**GitHub Pages**: Push build folder to gh-pages branch
**AWS S3**: Upload build folder to S3 bucket with CloudFront
**Firebase Hosting**: Deploy using Firebase CLI

```bash
npm run build
# Then deploy the build folder to your hosting service
```

## 📊 API Integration

The app fetches products from FakeStoreAPI:

- **Endpoint**: `https://fakestoreapi.com/products`
- **Response**: Array of products with id, title, price, description, category, image, rating
- **No Authentication Required**: Public API

Sample product object:

```json
{
  "id": 1,
  "title": "Product Title",
  "price": 109.95,
  "description": "Description",
  "category": "electronics",
  "image": "image-url",
  "rating": { "rate": 3.9, "count": 120 }
}
```

## ✅ Features Coming Soon

- Product filters by category
- Product search functionality
- Wishlist feature
- Checkout page
- User authentication
- Order history
- Product reviews and ratings
- Dark mode toggle

## 🐛 Troubleshooting

**Port 3000 already in use:**

```bash
# Change port
PORT=3001 npm start
```

**Dependencies not installing:**

```bash
rm -rf node_modules package-lock.json
npm install
```

**Build fails:**

```bash
npm run build -- --stats
```

## 📄 License

This project is open source and available for personal and commercial use.

## 👨‍💻 Author

Created as a modern React shopping cart implementation demonstrating best practices with React 19, TypeScript, and Material-UI.

---

**Last Updated**: March 2026
**React Version**: 19.2.4
**Status**: ✅ Production Ready
