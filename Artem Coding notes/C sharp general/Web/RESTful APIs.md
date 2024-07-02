![[rest.webp]]**An interface that two computer systems use to exchange information securely over the internet. They allow different applications to communicate with each other by making HTTP requests to access and manipulate web resources represented in a consistent format.**
#### **Key Concepts:**
- **Resources**: The fundamental concept of REST. Resources are identified by URLs (Uniform Resource Locators).
- **HTTP Methods**: Commonly used methods include:
    - `GET` - Retrieve data from the specified resource. This is used to request data from a server.
    - `POST` - Submit data to be processed to a specified resource. Often used to send form data or upload files.
    - `PUT` - Update a resource or create a new resource if it doesn't exist at the specified URL. Sends a complete updated version of the resource.
    - `PATCH` - Partially modify an existing resource. Sends only the changes to be applied, not the entire resource.
    - `DELETE` - Remove data.
    - `HEAD` - Similar to GET but retrieves only the headers, not the body. Useful for checking metadata or if a resource has changed.
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
#### 2. **What are RESTful best practices?**
**Answer**:
- Use meaningful resource names in URLs.
- Follow the HTTP method conventions.
- Keep APIs stateless.
- Use JSON for responses (common and lightweight).
- Provide pagination for large data sets.
- Implement error handling and return appropriate HTTP status codes.
#### 3. **Explain [idempotency](https://www.youtube.com/watch?v=XAccGbtl3Z8&ab_channel=AlexHyett) in RESTful APIs.**
**Answer**: [Idempotency](https://www.youtube.com/watch?v=XAccGbtl3Z8&ab_channel=AlexHyett) means that multiple identical requests should have the same effect as a single request. For example, `GET`, `PUT`, and `DELETE` methods should be idempotent, while `POST` typically is not.
#### 4. **What are the advantages of using REST?**
**Answer**:
- Scalability: Statelessness helps in scaling.
- Simplicity: Uses standard HTTP.
- Flexibility: Can use various formats like JSON, XML.
- Caching: HTTP caching mechanisms can be used to improve performance.
#### 5. **What is a RESTful resource?**
**Answer**: A RESTful resource is an object or representation of something, which is accessible through a unique URL and manipulated using standard HTTP methods.
#### 6. **What are some common HTTP status codes in RESTful APIs?**
**Answer**:
- `200 OK`: Successful GET or POST.
- `201 Created`: Successful resource creation.
- `204 No Content`: Successful request without body.
- `400 Bad Request`: Malformed request.
- `401 Unauthorized`: Authentication required.
- `403 Forbidden`: No permission to access.
- `404 Not Found`: Resource not found.
- `500 Internal Server Error`: Server error.
[[Pagination|Pagination by get vs post]]