# POS Backend (Spring Boot)

This project is a simple Point of Sale (POS) backend API built with Spring Boot.
It manages products, creates orders, records order-sale lines, and exposes REST endpoints
for product, order, and sales operations.
The repository also includes a lightweight static frontend in `front/` (HTML + jQuery + Bootstrap)
for dashboard, product management, and sales views.

## Tech Stack

- Java + Spring Boot
- Spring Web (REST controllers)
- Spring Data JPA
- MySQL
- Lombok
- HTML + jQuery + Bootstrap (frontend pages in `front/`)

## Project Structure

- `controller`: HTTP endpoints for products, orders, and sales
- `dao`: service/business layer for saving and querying data
- `entity`: JPA entities (`products`, `orders`, `sales`)
- `repository`: Spring Data JPA repositories
- `dto`: request DTOs such as `OrderDto`
- `front`: static frontend pages (`index.html`, `products.html`, `sales.html`)

## Main Features

- Add, update, delete, and fetch products
- Search product by barcode
- Save an order from a list of products with automatic total calculation
- Create sales records linked to each order item
- Retrieve all orders
- Retrieve all sales or sales by order id
- Use a simple browser-based frontend for POS operations

## API Endpoints

### Product APIs (`/products`)

- `POST /products/add-product`
- `POST /products/update-product`
- `GET /products/delete-product?productId={id}`
- `GET /products/get-by-barcode?barcode={value}`
- `GET /products/get-by-id?productId={id}`
- `GET /products/get-all-products`

### Order APIs (`/orders`)

- `POST /orders/save-order`
- `GET /orders/get-orders`

### Sales APIs (`/sales`)

- `GET /sales/get-sales`
- `GET /sales/get-by-order-id?orderId={id}`

## Frontend

The `front/` folder contains three static pages:

- `front/index.html`: dashboard and order checkout screen
- `front/products.html`: products listing and CRUD UI
- `front/sales.html`: orders and sales details UI

These pages use AJAX calls to `http://localhost:8081` and are intended to be opened
in a browser while the backend application is running.

## Configuration

Database and server settings are in `src/main/resources/application.properties`.
Current configuration points to:

- MySQL on `localhost:3306`
- database name: `database`
- username: `root`
- server port: `8081`

Update these values according to your local environment before running the app.