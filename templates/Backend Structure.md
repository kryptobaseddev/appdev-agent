### Comprehensive Backend Structure Template Instructions Using Supabase

This **Backend Structure Template** provides detailed guidance for creating consistent, scalable backend documentation tailored to the specific needs of a project as determined by **AppDev AI Agent**. It emphasizes using **Supabase** for database management, authentication, and content handling while ensuring alignment with the **Development Documentation** and **Development Guidelines**.

The output file `BackendStructure.md` should be in **Markdown format** to facilitate clarity, maintainability, and ease of collaboration.

---

### **1. Purpose of the Backend Structure Document**

- Define the backend architecture and organizational structure tailored to the project's needs.
- Standardize backend design to ensure scalability, security, and maintainability.
- Highlight Supabase integration for database, authentication, and content management.
- Serve as the primary reference document for developers during backend implementation.

---

### **2. Template Structure Overview**

The **Backend Structure Document** includes the following sections:

1. **Introduction**
   - Overview of the backend stack and guiding principles.
   - Key technologies and libraries used.

2. **Project Structure**
   - Directory organization and purpose of each folder.

3. **Supabase Integration**
   - Overview of Supabase services used: database, authentication, and storage.
   - Configuration and best practices.

4. **API Architecture**
   - Standards for building REST or GraphQL APIs.
   - Guidelines for endpoint design, error handling, and response structure.

5. **Database Design**
   - Schema structure and relationships.
   - Guidelines for migrations and seeding data.

6. **Authentication**
   - Implementation of Supabase’s authentication features.
   - Role-based access control (RBAC) and session management.

7. **Environment Variables**
   - Best practices for managing environment-specific configurations.

8. **Security Practices**
   - Guidelines for securing APIs, database, and sensitive data.

9. **Testing and Validation**
   - Tools and strategies for unit, integration, and end-to-end testing.

10. **Performance Optimization**
    - Techniques for improving backend efficiency and scalability.

---

### **3. Backend Structure Document Template**

The following Markdown template provides a consistent format for documenting the backend structure:

```markdown
# Backend Structure Documentation

## Introduction

This document outlines the backend architecture and design principles for the project. It leverages **Supabase** for database management, authentication, and content storage while ensuring scalability, security, and maintainability.

- **Backend Stack**: [Insert stack details, e.g., Node.js, Go, Python]
- **Key Libraries**: [Insert chosen libraries, e.g., Supabase JS Client, Express, Fastify]
- **Guiding Principles**: Scalability, security, modularity, and performance.

---

## Project Structure

```plaintext
src/
├── controllers/      # API endpoint logic
├── services/         # Business logic and Supabase integration
├── models/           # Database schema and query helpers
├── routes/           # Route definitions
├── middleware/       # Request validation and middleware logic
├── utils/            # Utility functions
├── config/           # Configuration and environment variables
├── tests/            # Test files for unit, integration, and end-to-end testing
└── migrations/       # Database migration scripts
```

### Folder Descriptions

1. **`controllers/`**: Contains the logic for handling API requests and responses.  
   - Example: `UserController.js` for managing user-related endpoints.

2. **`services/`**: Encapsulates business logic and interfaces with Supabase services.  
   - Example: `AuthService.js` for managing authentication flows.

3. **`models/`**: Includes database schema definitions and helper functions for database queries.  

4. **`routes/`**: Defines API routes and maps them to controllers.  

5. **`middleware/`**: Contains reusable middleware for validating requests and handling errors.  

6. **`utils/`**: Shared utility functions (e.g., date formatting, logging).  

7. **`config/`**: Stores configuration files and manages environment variables.  

8. **`tests/`**: Contains unit, integration, and end-to-end test cases.  

9. **`migrations/`**: Database migration scripts to maintain schema versions.

---

## Supabase Integration

### **Services Used**
- **Database**: Used for relational data storage and querying.
- **Authentication**: Handles user management, sign-ups, and session tokens.
- **Storage**: Manages file uploads and access.

### **Configuration**
1. Install Supabase client:
   ```bash
   npm install @supabase/supabase-js
   ```
2. Initialize Supabase:
   ```javascript
   import { createClient } from '@supabase/supabase-js';

   const supabase = createClient(process.env.SUPABASE_URL, process.env.SUPABASE_KEY);

   export default supabase;
   ```

3. Use `.env` for sensitive keys:
   ```plaintext
   SUPABASE_URL=https://your-instance.supabase.co
   SUPABASE_KEY=your-anon-or-service-key
   ```

---

## API Architecture

### **Endpoint Standards**
- Use REST or GraphQL depending on project requirements.
- Example route definition:
  ```javascript
  import express from 'express';
  import { getUser } from '../controllers/UserController';

  const router = express.Router();

  router.get('/user/:id', getUser);

  export default router;
  ```

### **Error Handling**
- Centralized error handler in `middleware/`:
  ```javascript
  const errorHandler = (err, req, res, next) => {
      console.error(err.stack);
      res.status(500).send({ error: 'Internal Server Error' });
  };

  export default errorHandler;
  ```

---

## Database Design

### **Schema and Relationships**
- Define schemas in Supabase SQL editor or use migration scripts.
- Example table structure:
  ```sql
  CREATE TABLE profiles (
      id UUID PRIMARY KEY,
      username TEXT NOT NULL UNIQUE,
      created_at TIMESTAMP DEFAULT NOW()
  );
  ```

### **Migrations**
- Store migration scripts in the `migrations/` directory.
- Example migration:
  ```sql
  ALTER TABLE profiles ADD COLUMN bio TEXT;
  ```

---

## Authentication

### **Implementation**
- Configure Supabase authentication with JWT:
  ```javascript
  const { user, error } = await supabase.auth.signInWithPassword({
      email: 'test@example.com',
      password: 'password123',
  });
  ```

### **Role-Based Access Control (RBAC)**
- Use Supabase policies to enforce permissions:
  ```sql
  CREATE POLICY "Users can view their own profile"
  ON profiles
  FOR SELECT
  USING (auth.uid() = id);
  ```

---

## Environment Variables

### **Best Practices**
- Store environment-specific variables in `.env`:
  ```plaintext
  SUPABASE_URL=https://your-instance.supabase.co
  SUPABASE_KEY=your-anon-or-service-key
  JWT_SECRET=your-jwt-secret
  ```
- Use a centralized `config.js` file for consistent access:
  ```javascript
  export const config = {
      supabaseUrl: process.env.SUPABASE_URL,
      supabaseKey: process.env.SUPABASE_KEY,
      jwtSecret: process.env.JWT_SECRET,
  };
  ```

---

## Security Practices

1. Use HTTPS for all communication.
2. Secure API endpoints with JWT authentication.
3. Apply database policies for row-level security.
4. Regularly rotate Supabase service keys.

---

## Testing and Validation

- Use testing tools such as Jest, Mocha, or Supertest.
- Example test:
  ```javascript
  import request from 'supertest';
  import app from '../app';

  describe('GET /user/:id', () => {
      it('should return user data', async () => {
          const res = await request(app).get('/user/1');
          expect(res.statusCode).toBe(200);
          expect(res.body).toHaveProperty('username');
      });
  });
  ```

---

## Performance Optimization

1. Use caching for frequent queries.
2. Optimize database indexes.
3. Use Supabase’s real-time features only when necessary to reduce overhead.

---

This template ensures a scalable, secure, and consistent backend structure tailored to the project’s specific needs, with seamless integration of Supabase for core backend services.
``` 
