# FastAPI Chai Menu API

A simple read-only REST API for serving chai, snacks, and combo menu items. Built with FastAPI and Pydantic.

## Features

- View the complete menu
- Filter menu items by category
- Retrieve a menu item by ID
- Automatic request validation and API documentation
- JSON responses using Pydantic models

## Tech Stack

- Python 3.10+
- FastAPI
- Uvicorn
- Pydantic

## Project Structure

```text
.
├── `main.py`          # FastAPI application and routes
├── `models.py`        # Pydantic response models
├── `data.py`          # In-memory menu data
└── `requirements.txt` # Project dependencies
```

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/fastapi-chai-menu-api.git
cd fastapi-chai-menu-api
```

Create and activate a virtual environment:

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### macOS/Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

## Running the API

```bash
uvicorn main:app --reload
```

The API will be available at:

```text
http://127.0.0.1:8000
```

## API Documentation

FastAPI automatically provides interactive documentation:

- Swagger UI: http://127.0.0.1:8000/docs
- ReDoc: http://127.0.0.1:8000/redoc

## Endpoints

### Welcome

```http
GET /
```

### Get the complete menu

```http
GET /menu
```

### Filter by category

```http
GET /menu?category=chai
GET /menu?category=snacks
GET /menu?category=combos
```

### Get a menu item by ID

```http
GET /menu/1
```

## Example Response

```json
{
  "status": "success",
  "count": 1,
  "items": [
    {
      "id": 1,
      "name": "Masala Chai",
      "category": "chai",
      "price": 30.0,
      "description": "Classic Indian spiced tea with ginger and cardamom",
      "available": true
    }
  ]
}
```

## Current Limitations

- Menu data is stored in memory
- The API is read-only
- No authentication or database integration is included
