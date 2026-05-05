\## Question 1: Difference between unary, server streaming, and bi-directional streaming in gRPC  



Unary is a simple request-response pattern where one request gives one response, so it fits basic operations like login or payments. Server streaming allows one request to return multiple responses over time, which is useful for things like transaction history or logs. Bi-directional streaming allows both sides to continuously send messages, making it suitable for real-time cases like chat, but it is more complex to handle.  





\## Question 2: Security considerations in Rust gRPC  



Security in gRPC involves controlling access and protecting data during communication. Authentication is used to verify identity, authorization controls what actions are allowed, and encryption (usually TLS) protects data from being read by others. If these are not handled properly, it can lead to unauthorized access or data exposure.  





\## Question 3: Challenges in bidirectional streaming  



Bidirectional streaming can be difficult because both sides are sending data at the same time. Issues can include messages arriving out of order, dropped connections, and resource problems if too many messages are processed. In cases like chat systems, handling multiple users and keeping communication consistent adds more complexity.  





\## Question 4: Advantages and disadvantages of ReceiverStream  



ReceiverStream is useful because it works easily with Tokio channels and allows asynchronous data to be sent as a stream, making it simple to implement. However, it is quite basic and does not provide much control for advanced cases like managing backpressure or complex stream behavior, so it may not be ideal for larger systems.  





\## Question 5: Improving code reuse and modularity  



Code can be made more reusable by organizing it into separate parts such as services, data models, and helper functions instead of keeping everything in one place. Separating business logic from gRPC handling and reusing shared functionality helps make the code easier to maintain and extend over time.  





\## Question 6: Handling more complex payment processing  



More advanced payment handling would require additional steps such as validating inputs, checking balances, handling errors properly, and connecting to a database. It may also include ensuring transaction safety, preventing duplicate operations, and adding logging or monitoring for reliability.  





\## Question 7: Impact of gRPC on system design  



Using gRPC encourages strongly defined APIs through Protocol Buffers, which improves performance and consistency between services. It works well in service-to-service communication, but integration with systems that rely on REST or JSON may require additional layers or adjustments.  





\## Question 8: HTTP/2 vs HTTP/1.1 and WebSocket  



HTTP/2 provides better performance through features like multiplexing and streaming, making it more efficient than HTTP/1.1. However, it is more complex and not as widely supported in some environments compared to HTTP/1.1 or WebSocket, which are simpler and more commonly used for web-based applications.  





\## Question 9: REST vs gRPC communication model  



REST uses a request-response model where each interaction requires a new request, which is less suitable for real-time communication. gRPC supports streaming, allowing continuous data exchange, which improves responsiveness for real-time scenarios like live updates or chat, but adds more complexity.  





\## Question 10: Protocol Buffers vs JSON  



Protocol Buffers use a strict schema, which makes communication more efficient and consistent but less flexible when changes are needed. JSON is more flexible and easier to modify, but it can lead to inconsistencies and is generally less efficient due to its lack of strict structure.

