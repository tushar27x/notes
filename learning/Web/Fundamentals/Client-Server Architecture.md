- A distributed system architecture that partitions tasks between providers of a resource or service (server) and the service requester(client).
- **Client** is a computer (***Host***) i.e. capable of receiving information or using a particular service from the service providers (***Servers***).
- **Server** is a remote computer that provides information (data) or access to particular services.

![client-server model](https://media.geeksforgeeks.org/wp-content/uploads/20231128175510/Client-Server-Model-2.png)

### Steps 
1. User enters a URL.
2. **DNS** server looks up the address of the web server.
3. The browsers sends a HTTP/HTTPS request to the web server.
4. The server sends the necessary files to the browser.
5. The browser render the files and website is displayed. This rendering is done with the help of **DOM** (Document Object Model) interpreter, **CSS** interpreter, and **JS Engine** collectively known as the **JIT** or (Just in Time) Compilers.

## Advantages of Client-Server Model

- Centralized system with all data in a single place.
- Cost efficient requires less maintenance cost and Data recovery is possible.
- The capacity of the Client and Servers can be changed separately.

## Disadvantages of Client-Server Model

- Clients are prone to viruses, Trojans, and worms if present in the Server or uploaded into the Server.
- Servers are prone to DoS (Denial of Service) attacks.
- Data packets may be spoofed or modified during transmission.
- Phishing or capturing login credentials or other useful information of the user are common and MITM(Man In The Middle) attacks are common.