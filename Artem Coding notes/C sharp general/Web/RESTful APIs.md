![[rest.webp]]**An interface that two computer systems use to exchange information securely over the internetThey allow different applications to communicate with each other by making HTTP requests to access and manipulate web resources represented in a consistent format.**

**Key Concepts:**
- **Resources**: The fundamental concept of REST. Resources are identified by URLs (Uniform Resource Locators).
- **HTTP Methods**: Commonly used methods include:
    - `GET` - Retrieve data.
    - `POST` - Submit data to be processed.
    - `PUT` - Update data.
    - `DELETE` - Remove data.
- **Stateless**: Each request from client to server must contain all the information the server needs to fulfill the request.
- **Representations**: Resources are represented in formats such as JSON, XML, HTML, etc.
- **Idempotency**: Operations like `GET`, `PUT`, and `DELETE` should be idempotent, meaning repeated execution should yield the same result.
**Usage:**
- **Web Services**: Integrating different services, allowing them to communicate.
- **Microservices Architecture**: Enabling individual services to interact.
- **Mobile Applications**: Backend communication.
- **IoT**: Device communication.
### Popular Interview Questions
#### 1. **What is REST?**
**Answer**: REST stands for Representational State Transfer, a set of architectural principles for designing networked applications. It uses stateless communication, relies on standard HTTP methods, and represents resources in a consistent format.
#### 2. **What are the main HTTP methods used in RESTful APIs and what are their purposes?**
**Answer**:
- `GET`: Retrieve data from a server.
- `POST`: Submit data to the server.
- `PUT`: Update existing data.
- `DELETE`: Remove data.
- `PATCH`: Partially update existing data.
#### 3. **What is the difference between PUT and POST?**
**Answer**:
- `PUT` is idempotent; it updates an existing resource or creates a new one if it does not exist, using the same URL.
- `POST` is not idempotent; it creates a new resource, and subsequent identical requests will create duplicates.
#### 4. **What are RESTful best practices?**
**Answer**:
- Use meaningful resource names in URLs.
- Follow the HTTP method conventions.
- Keep APIs stateless.
- Use JSON for responses (common and lightweight).
- Provide pagination for large data sets.
- Implement error handling and return appropriate HTTP status codes.
#### 5. **Explain [idempotency](https://www.youtube.com/watch?v=XAccGbtl3Z8&ab_channel=AlexHyett) in RESTful APIs.**
**Answer**: [Idempotency](https://www.youtube.com/watch?v=XAccGbtl3Z8&ab_channel=AlexHyett) means that multiple identical requests should have the same effect as a single request. For example, `GET`, `PUT`, and `DELETE` methods should be idempotent, while `POST` typically is not.
#### 6. **What are the advantages of using REST?**
**Answer**:
- Scalability: Statelessness helps in scaling.
- Simplicity: Uses standard HTTP.
- Flexibility: Can use various formats like JSON, XML.
- Caching: HTTP caching mechanisms can be used to improve performance.
#### 7. **What is a RESTful resource?**
**Answer**: A RESTful resource is an object or representation of something, which is accessible through a unique URL and manipulated using standard HTTP methods.
#### 8. **What are some common HTTP status codes in RESTful APIs?**
**Answer**:
- `200 OK`: Successful GET or POST.
- `201 Created`: Successful resource creation.
- `204 No Content`: Successful request without body.
- `400 Bad Request`: Malformed request.
- `401 Unauthorized`: Authentication required.
- `403 Forbidden`: No permission to access.
- `404 Not Found`: Resource not found.
- `500 Internal Server Error`: Server error.
[[Pagination]]