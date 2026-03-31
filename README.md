# 🌍 Travel Discovery Microservice

A Java-based **Dropwizard microservice** that enables users to search for hotels and rental car services in the **Hoen Archipelago**, an emerging tourist destination.

---

## 📌 Overview

As part of Skyscanner’s expansion, this service allows the backend system to query travel data for a given city and return relevant:

* 🏨 Hotels
* 🚗 Rental Cars

The service follows a **microservice architecture**, ensuring modularity, scalability, and ease of deployment.

---

## ⚙️ How It Works

1. A POST request is sent with a city name.
2. The service reads data from:

   * `hotels.json`
   * `rental_cars.json`
3. Filters results based on the requested city.
4. Returns matching results as JSON.

---

## 📡 API Endpoint

### 🔹 Search

```id="nwr5y6"
POST /search
```

### Request Body

```json id="2b31a7"
{
  "city": "petalborough"
}
```

### Response

```json id="5xw1qg"
[
  {
    "city": "petalborough",
    "title": "Sea Breeze Hotel",
    "kind": "hotel"
  },
  {
    "city": "petalborough",
    "title": "Island Rentals",
    "kind": "rental_car"
  }
]
```

---

## 🏗️ Project Structure

```id="b5px5h"
src/main/java/com/skyscanner/
│── HoenScannerApplication.java   # Main application
│── Search.java                   # Request model
│── SearchResult.java             # Response model
│── SearchResource.java           # REST endpoint

src/main/resources/
│── hotels.json
│── rental_cars.json
```

---

## 🛠️ Tech Stack

* Java
* Dropwizard
* Jackson (JSON parsing)
* Maven

---

## 🚀 Running the Application

### 1. Build the project

```id="y4j1b3"
mvn clean package
```

### 2. Run the service

```id="q6lq3v"
java -jar target/travel-discovery-service.jar server config.yml
```

---

## 🧪 Testing the API

Use Postman or curl:

```id="vdbv7t"
POST http://localhost:8080/search
```

Body:

```json id="8h1j2p"
{
  "city": "rustburg"
}
```

---

## 💡 Key Concepts

* Microservice architecture
* RESTful API design
* Data filtering using Java Streams
* JSON serialization/deserialization

---

## 🌱 Future Improvements

* Add partial search (not exact match)
* Add pagination
* Integrate with real APIs
* Add Swagger documentation
* Add caching for performance

---

## 👩‍💻 Author

Siddhi Mirgule

---
