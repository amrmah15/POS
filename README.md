# POS Backend (Spring Boot)

This project is a simple Point of Sale (POS) backend API built with Spring Boot.
It manages products, creates orders, records order-sale lines, and exposes REST endpoints
for product, order, and sales operations.

## Tech Stack

- Java + Spring Boot
- Spring Web (REST controllers)
- Spring Data JPA
- MySQL
- Lombok

## Project Structure

- `controller`: HTTP endpoints for products, orders, and sales
- `dao`: service/business layer for saving and querying data
- `entity`: JPA entities (`products`, `orders`, `sales`)
- `repository`: Spring Data JPA repositories
- `dto`: request DTOs such as `OrderDto`

## Main Features

- Add, update, delete, and fetch products
- Search product by barcode
- Save an order from a list of products with automatic total calculation
- Create sales records linked to each order item
- Retrieve all orders
- Retrieve all sales or sales by order id

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

## Configuration

Database and server settings are in `src/main/resources/application.properties`.
Current configuration points to:

- MySQL on `localhost:3306`
- database name: `database`
- username: `root`
- server port: `8081`

Update these values according to your local environment before running the app.