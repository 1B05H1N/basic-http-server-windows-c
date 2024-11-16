### README: Simple Web Server in C for Windows

---

#### Description
This project is a simple C program that demonstrates how to implement a basic web server on Windows. It is designed as a **learning exercise** to familiarize beginners with:
- Network programming concepts.
- Socket API usage on Windows.
- HTTP response generation.

When executed, the server listens on port `8080` for incoming HTTP requests and responds with a simple HTML page.

---

#### Disclaimer: **Not Secure**
This program is for **educational purposes only** and should **not** be used in production environments or deployed on public networks. It lacks:
- Proper error handling for complex cases.
- Authentication mechanisms.
- Protection against security vulnerabilities such as buffer overflows, DoS attacks, or malicious requests.

**Use this program at your own risk.**

---

#### Features
- Implements a basic HTTP/1.1 server.
- Listens on port `8080`.
- Responds with an HTML page containing "Hello there, this is a simple web server!"

---

#### Prerequisites
To compile and run this program, you need:
- A Windows operating system.
- GCC compiler (MinGW or MSYS2) installed.
- Basic knowledge of C programming.

---

#### How to Compile and Run

1. **Clone or Download the Project**:
   Save the program code into a file named `webserver.c`.

2. **Install a GCC Compiler**:
   - Install MinGW or MSYS2. 
   - Ensure `gcc` is available in your system path.

3. **Compile the Code**:
   Open a terminal and navigate to the directory containing `webserver.c`. Run the following command to compile:

   ```bash
   gcc webserver.c -o webserver -lws2_32
   ```

   This links the Winsock library (`Ws2_32.lib`) required for network programming.

4. **Run the Server**:
   Execute the compiled program:

   ```bash
   ./webserver
   ```

5. **Access the Server**:
   - Open a web browser and visit: `http://localhost:8080`.
   - Alternatively, use a tool like `curl`:
     ```bash
     curl http://localhost:8080
     ```

6. **Stop the Server**:
   Press `Ctrl+C` in the terminal to terminate the server.

---

#### Example HTTP Response
When a client connects, the server responds with:

```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 81

<html><body><h1>Hello there,</h1><p>this is a simple web server!</p></body></html>
```

---

#### Notes
- **This is a minimal and insecure example for learning purposes.**
- The program currently handles one request at a time in a blocking manner.
- It does not sanitize input or prevent malicious activity.

---

#### Troubleshooting
1. **"Port 8080 already in use" Error**:
   - Ensure no other application (e.g., another web server or service) is using port `8080`.
   - Modify the `#define PORT` line in the code to change the listening port.

2. **Firewall Blocking the Program**:
   - Allow the program through your firewall settings.

3. **Undefined References to Winsock Functions**:
   - Ensure you added `-lws2_32` when compiling with GCC.

---

#### Important: Security Risks
This code is deliberately simple and lacks the safeguards necessary for secure network programming. **Do not expose this server to the internet or use it for anything beyond learning.**

Common risks include:
- **Buffer Overflows**: Insufficient input validation may allow attackers to execute arbitrary code.
- **DoS Attacks**: The server does not handle multiple requests efficiently or securely.
- **Data Interception**: Connections are unencrypted and susceptible to man-in-the-middle attacks.

For secure web server development, consider using well-tested libraries and frameworks (e.g., Apache, Nginx, or Python's Flask).

---

#### License
This project is provided for educational purposes under the MIT License. Use, modify, and distribute at your own risk.

---