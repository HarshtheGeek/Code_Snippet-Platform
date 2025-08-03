# Code_Snippet-Platform

Here's a detailed and professional **README.md** project description for your **Live Code Snippet Sharing Platform**:

---

# 🔥 Live Code Snippet Sharing Platform

A real-time collaborative platform where users can **create, update, delete, and share code snippets**. The application uses **GraphQL** for flexible API access, **WebSocket** for real-time broadcasting, and Node.js's built-in **fs** and **path** modules for secure file storage.

---

## 📌 Features

* 🚀 **Create, Read, Update, and Delete (CRUD)** code snippets
* ⚡ **Real-time broadcast** of snippet changes to all connected users via WebSocket
* 📂 Snippets are securely saved as text files using Node's `fs` and `path` modules
* 📡 **GraphQL API** allows precise querying and mutations
* 🧪 Built-in support for testing via **GraphiQL** interface

---

## 🛠️ Tech Stack

| Layer     | Technology                            |
| --------- | ------------------------------------- |
| Runtime   | Node.js                               |
| API       | GraphQL                               |
| Real-Time | WebSocket (`ws`)                      |
| File I/O  | `fs`, `path`                          |
| Server    | Express.js                            |
| Client    | (Optional) React + Apollo + WebSocket |

---

## 🧠 Architecture Overview

```bash
GraphQL API ──> Node.js Backend ──> FS (local file storage)
                     │
                     ▼
            WebSocket Broadcasts
                     │
                     ▼
               All Connected Clients
```

---

## 🧪 Example GraphQL Queries

### 📥 Get a Snippet

```graphql
query {
  getSnippet(name: "example") {
    name
    content
  }
}
```

### 📤 Create or Update a Snippet

```graphql
mutation {
  createSnippet(name: "example", content: "console.log('Hello World')") 
}
```

---

## ⚙️ Installation

```bash
git clone https://github.com/yourusername/snippet-share.git
cd snippet-share/server
npm install
node index.js
```

> Server runs at: [http://localhost:4000/graphql](http://localhost:4000/graphql)

---

## 🔌 WebSocket Endpoint

WebSocket server runs on the same port (`ws://localhost:4000`).
When a snippet is **created, updated, or deleted**, a broadcast is sent to all connected clients in the following format:

```json
{
  "type": "created" | "updated" | "deleted",
  "name": "example"
}
```

---

## 📁 Directory Structure

```
/server
  ├── /snippets         # Saved snippet files
  ├── index.js          # Entry point
  ├── graphql.js        # GraphQL resolvers
  ├── wsServer.js       # WebSocket logic
  └── schema.graphql    # GraphQL schema definition
```

---

## 🧩 Possible Improvements

* Add user authentication (JWT or OAuth)
* Syntax highlighting on the frontend
* MongoDB/PostgreSQL storage instead of file system
* Frontend with collaborative editing like Google Docs

---

## 📄 License

MIT License

---

Would you like me to generate the README as a downloadable file? Or include a simple React frontend example too?
