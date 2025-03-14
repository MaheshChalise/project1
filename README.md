
# Python API Server

This is a simple Python API Server using POST to save data to MongoDB and GET requests to receive the data from MongoDB.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- You have installed Python 3.6 or higher.
- You have a basic understanding of Python projects and virtual environments.

## Installation

### Setting Up a Virtual Environment

To avoid conflicts with other Python projects you may be working on, it's a good idea to use a virtual environment. Here's how you can set one up:

**For macOS and Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

**For Windows:**

```cmd
python -m venv venv
.\venv\Scripts\activate
```

### Installing Dependencies

Once your virtual environment is activated, install the project dependencies by running:

```bash
pip install -r requirements.txt
```

## Running the Application

To start the server, run:

```bash
python app.py
```
created image named project1
```
docker build -t  project1
```

Tagged image file to the respected repository
```bash
docker tag project1 maheshchalise/project1:latest
```
pushed the image to the repository
```
docker push maheshchalise/project1:latest  
```
created docker network named nw1
```
docker network create nw1 
```
runs a detached container named pythonapp on network nw1, mapping port 3000, using the image maheshchalise/project1:latest
```
 docker run -d -p 3000:3000 --network nw1 --name pythonapp maheshchalise/project1:latest
```
Ensure your MongoDB instance is running and accessible as configured in your Python script.
```bash
docker run --name mongodb-container -d -p 27017:27017 -v my_mongo_data:/data/db mongo:latest
```


## Using the Application

To interact with the application, you can use the following `curl` command to create a new item in the database:

```bash
curl -X POST http://localhost:3000/items \
     -H "Content-Type: application/json" \
     -d '{"id": "4", "name": "mahesh"}'
```

## Contributing to the Project

Contributions to enhance the project are welcome. Please fork the repository and create a pull request.

## License

This project is licensed under the GPLv3.

---

