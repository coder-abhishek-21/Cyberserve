# CyberServe - Database Schema Reference

This document outlines the database structure for backend integration.

## 📊 Database Tables

### 1. Users Table

```sql
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    user_code VARCHAR(10) UNIQUE NOT NULL,  -- U1001, U1002, etc.
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    mobile VARCHAR(10) NOT NULL,
    address TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    is_active BOOLEAN DEFAULT TRUE
);
```

**Example Data:**
```
user_id: 1
user_code: U1001
name: John Doe
email: john@example.com
password_hash: $2y$10$... (bcrypt hash)
mobile: 9876543210
address: 123 Main Street, City
```

---

### 2. Admins Table

```sql
CREATE TABLE admins (
    admin_id INT PRIMARY KEY AUTO_INCREMENT,
    admin_code VARCHAR(10) UNIQUE NOT NULL,  -- ADMIN001, etc.
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    mobile VARCHAR(10) NOT NULL,
    address TEXT NOT NULL,
    center_timing VARCHAR(50),  -- "9:00 AM - 9:00 PM"
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    is_active BOOLEAN DEFAULT TRUE
);
```

**Example Data:**
```
admin_id: 1
admin_code: ADMIN001
name: CyberServe Admin
email: admin@cyberserve.com
password_hash: $2y$10$... (bcrypt hash)
mobile: 9876543210
address: CyberServe Center, Main Street
center_timing: 9:00 AM - 9:00 PM
```

---

### 3. Services Table

```sql
CREATE TABLE services (
    service_id INT PRIMARY KEY AUTO_INCREMENT,
    service_code VARCHAR(20) UNIQUE NOT NULL,
    service_name VARCHAR(100) NOT NULL,
    description TEXT,
    price INT NOT NULL,
    is_active BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**Example Data:**
```
service_id: 1, service_code: AADHAAR, service_name: Aadhaar Update, price: 50
service_id: 2, service_code: PAN, service_name: PAN Card Apply, price: 100
service_id: 3, service_code: EXAM, service_name: Online Exam Form, price: 80
service_id: 4, service_code: PRINT, service_name: Printout (per page), price: 5
service_id: 5, service_code: SCAN, service_name: Scan & Email, price: 20
service_id: 6, service_code: VOTER, service_name: Voter ID Apply, price: 70
service_id: 7, service_code: BANK, service_name: Bank Seva (KYC), price: 60
service_id: 8, service_code: TRAIN, service_name: Train Ticket Booking, price: 40
service_id: 9, service_code: CERT, service_name: Online Certificate Download, price: 50
service_id: 10, service_code: DEVICE, service_name: Device Related Work, price: 100
service_id: 11, service_code: PAYMENT, service_name: Online Payment Help, price: 30
service_id: 12, service_code: PDF, service_name: PDF Related Work, price: 15
```

---

### 4. Service Requests Table

```sql
CREATE TABLE service_requests (
    request_id INT PRIMARY KEY AUTO_INCREMENT,
    request_code VARCHAR(20) UNIQUE NOT NULL,  -- REQ20240101001, etc.
    user_id INT NOT NULL,
    admin_id INT,
    total_amount INT NOT NULL,
    payment_reference VARCHAR(100),
    payment_screenshot_url VARCHAR(255),
    notes TEXT,
    status ENUM('Pending', 'Accepted', 'Processing', 'Completed', 'Rejected') DEFAULT 'Pending',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    completed_at TIMESTAMP NULL,
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (admin_id) REFERENCES admins(admin_id)
);
```

**Example Data:**
```
request_id: 1
request_code: REQ20240101001
user_id: 1
admin_id: 1
total_amount: 150
payment_reference: UPI123456789
status: Accepted
created_at: 2024-01-01 10:30:00
```

---

### 5. Request Services Table (Many-to-Many)

```sql
CREATE TABLE request_services (
    id INT PRIMARY KEY AUTO_INCREMENT,
    request_id INT NOT NULL,
    service_id INT NOT NULL,
    quantity INT DEFAULT 1,
    price INT NOT NULL,
    FOREIGN KEY (request_id) REFERENCES service_requests(request_id),
    FOREIGN KEY (service_id) REFERENCES services(service_id),
    UNIQUE KEY unique_request_service (request_id, service_id)
);
```

**Example Data:**
```
id: 1, request_id: 1, service_id: 1, quantity: 1, price: 50
id: 2, request_id: 1, service_id: 2, quantity: 1, price: 100
```

---

### 6. Contact Messages Table

```sql
CREATE TABLE contact_messages (
    message_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    phone VARCHAR(10),
    subject VARCHAR(200) NOT NULL,
    message TEXT NOT NULL,
    is_read BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**Example Data:**
```
message_id: 1
name: Jane Smith
email: jane@example.com
phone: 9876543211
subject: Service Inquiry
message: I would like to know more about your services...
is_read: FALSE
```

---

### 7. Payments Table (Optional)

```sql
CREATE TABLE payments (
    payment_id INT PRIMARY KEY AUTO_INCREMENT,
    request_id INT NOT NULL,
    amount INT NOT NULL,
    payment_method VARCHAR(50),  -- UPI, Card, Cash, etc.
    transaction_id VARCHAR(100) UNIQUE,
    payment_status ENUM('Pending', 'Completed', 'Failed') DEFAULT 'Pending',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (request_id) REFERENCES service_requests(request_id)
);
```

---

### 8. Audit Log Table (Optional)

```sql
CREATE TABLE audit_logs (
    log_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    admin_id INT,
    action VARCHAR(100),
    entity_type VARCHAR(50),  -- User, Request, Service, etc.
    entity_id INT,
    old_value TEXT,
    new_value TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (admin_id) REFERENCES admins(admin_id)
);
```

---

## 🔑 Key Relationships

```
Users (1) ──→ (Many) Service Requests
Admins (1) ──→ (Many) Service Requests
Service Requests (1) ──→ (Many) Request Services
Services (1) ──→ (Many) Request Services
Service Requests (1) ──→ (Many) Payments
```

---

## 📋 Sample SQL Queries

### Get User with All Requests
```sql
SELECT 
    u.user_code,
    u.name,
    u.email,
    sr.request_code,
    sr.total_amount,
    sr.status,
    sr.created_at
FROM users u
LEFT JOIN service_requests sr ON u.user_id = sr.user_id
WHERE u.user_id = 1
ORDER BY sr.created_at DESC;
```

### Get Request with Services
```sql
SELECT 
    sr.request_code,
    s.service_name,
    rs.price,
    sr.total_amount,
    sr.status
FROM service_requests sr
JOIN request_services rs ON sr.request_id = rs.request_id
JOIN services s ON rs.service_id = s.service_id
WHERE sr.request_id = 1;
```

### Get Pending Requests
```sql
SELECT 
    sr.request_code,
    u.name,
    u.mobile,
    sr.total_amount,
    sr.created_at
FROM service_requests sr
JOIN users u ON sr.user_id = u.user_id
WHERE sr.status = 'Pending'
ORDER BY sr.created_at ASC;
```

### Get Admin Statistics
```sql
SELECT 
    COUNT(*) as total_requests,
    SUM(CASE WHEN status = 'Pending' THEN 1 ELSE 0 END) as pending,
    SUM(CASE WHEN status = 'Accepted' THEN 1 ELSE 0 END) as accepted,
    SUM(CASE WHEN status = 'Completed' THEN 1 ELSE 0 END) as completed,
    SUM(total_amount) as total_revenue
FROM service_requests;
```

---

## 🔐 Security Considerations

1. **Password Storage**: Use bcrypt or argon2 for hashing
2. **SQL Injection**: Use prepared statements
3. **Authentication**: Implement JWT or session-based auth
4. **Authorization**: Check user permissions before operations
5. **Data Validation**: Validate all inputs
6. **Encryption**: Encrypt sensitive data in transit (HTTPS)
7. **Audit Logging**: Log all important actions

---

## 📈 Indexing Strategy

```sql
-- User lookups
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_user_code ON users(user_code);

-- Request lookups
CREATE INDEX idx_requests_user_id ON service_requests(user_id);
CREATE INDEX idx_requests_admin_id ON service_requests(admin_id);
CREATE INDEX idx_requests_status ON service_requests(status);
CREATE INDEX idx_requests_created_at ON service_requests(created_at);

-- Service lookups
CREATE INDEX idx_services_service_code ON services(service_code);

-- Request services
CREATE INDEX idx_request_services_request_id ON request_services(request_id);
CREATE INDEX idx_request_services_service_id ON request_services(service_id);
```

---

## 🔄 Data Migration from Frontend

When migrating from localStorage to database:

1. Export localStorage data to JSON
2. Parse and validate data
3. Insert into respective tables
4. Verify data integrity
5. Update frontend to use API endpoints

---

## 📱 API Endpoints (Recommended)

```
POST   /api/auth/signup
POST   /api/auth/login
POST   /api/auth/logout
GET    /api/users/{id}
PUT    /api/users/{id}

POST   /api/requests
GET    /api/requests
GET    /api/requests/{id}
PUT    /api/requests/{id}
DELETE /api/requests/{id}

GET    /api/admin/dashboard
GET    /api/admin/requests
PUT    /api/admin/requests/{id}/status

POST   /api/contact
GET    /api/contact (admin only)
```

---

**Note**: This schema is designed to be flexible and scalable. Adjust based on specific requirements.
