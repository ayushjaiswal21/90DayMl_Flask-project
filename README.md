# 90DayML Flask Project

This repository contains a collection of Python modules and Flask applications developed as part of a 90-day Machine Learning journey, focusing on Flask web development fundamentals.

## Project Structure

```
90DayMl_Flask project/
├── README.md
├── mymodule.py           # Basic utility functions (square, double)
├── test_mymodule.py      # Unit tests for mymodule
├── sample1.py            # Basic Python addition example
├── lab/
│   └── server.py         # Main Flask REST API server
├── hjbsk-build_deploy_app_flask/  # Flask deployment examples
├── obmnl-flask_assignment/        # Flask assignments
└── __pycache__/          # Python bytecode cache
```

## Components

### 1. Core Modules

#### `mymodule.py`
Contains basic mathematical utility functions:
- `square(number)`: Returns the square of a given number
- `double(number)`: Returns twice the value of a given number

#### `test_mymodule.py`
Comprehensive unit tests for the mymodule functions using Python's unittest framework.

#### `sample1.py`
Basic Python script demonstrating:
- Function definition and usage
- Variable initialization
- String formatting with `.format()`

### 2. Flask REST API (`lab/server.py`)

A comprehensive Flask web application featuring:

#### Endpoints:
- `GET /` - Hello world endpoint
- `GET /no_content` - Returns 204 No Content status
- `GET /exp` - Explicit response with 200 status
- `GET /data` - Check data availability and length
- `GET /name_search?q=<query>` - Search persons by first name
- `GET /count` - Get count of persons in database
- `GET /person/<uuid:id>` - Find person by UUID
- `DELETE /person/<uuid:id>` - Delete person by UUID
- `POST /person` - Add new person to database

#### Features:
- In-memory data storage with sample person records
- UUID-based person identification
- Comprehensive error handling (400, 404, 422, 500)
- Query parameter validation
- JSON request/response handling

## Getting Started

### Prerequisites
- Python 3.7+
- Flask

### Installation
```bash
pip install flask
```

### Running the Flask Server
```bash
cd "C:\Users\pc\Desktop\90DayMl_Flask project\lab"
python server.py
```

The server will start in debug mode and be available at `http://localhost:5000`.

### Running Tests
```bash
python test_mymodule.py
```

## API Usage Examples

### Search for a person:
```bash
curl "http://localhost:5000/name_search?q=Tanya"
```

### Get all persons count:
```bash
curl "http://localhost:5000/count"
```

### Get person by ID:
```bash
curl "http://localhost:5000/person/3b58aade-8415-49dd-88db-8d7bce14932a"
```

### Add a new person:
```bash
curl -X POST "http://localhost:5000/person" \
  -H "Content-Type: application/json" \
  -d '{"id": "new-uuid", "first_name": "John", "last_name": "Doe"}'
```

## Development Notes

This project demonstrates:
- Basic Python programming concepts
- Unit testing with unittest
- Flask web framework fundamentals
- REST API design principles
- Error handling and status codes
- Query parameter validation
- JSON data manipulation

## License

This project is part of a learning exercise for the 90DayML program.
