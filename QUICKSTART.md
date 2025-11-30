# CyberServe - Quick Start Guide

## 🚀 How to Use the Website

### Step 1: Access the Website
Open your browser and go to:
```
http://localhost/CyberServeapp/
```

---

## 👥 User Portal Guide

### 1. **Create a New Account**
- Click **Login** → **User Signup**
- Fill in your details:
  - Full Name
  - Email
  - Mobile Number (10 digits)
  - Address
  - Password (minimum 6 characters)
- Click **Create Account**
- Your User ID will be auto-generated (e.g., U1001)

### 2. **Login to Your Account**
- Click **Login** → **User Login**
- Enter your email and password
- Click **Login**
- You'll be redirected to your dashboard

### 3. **View Your Dashboard**
- See your profile information
- View admin contact details and working hours
- Quick access to create new service requests

### 4. **Create a Service Request**
- Click **New Request** in the navbar
- Your information is auto-filled
- Select the services you need (you can select multiple):
  - Aadhaar Update (₹50)
  - PAN Card (₹100)
  - Online Exam Form (₹80)
  - Printout (₹5)
  - Scan & Email (₹20)
  - Voter ID (₹70)
  - Bank KYC (₹60)
  - Train Ticket (₹40)
  - Online Certificate (₹50)
  - Device Related (₹100)
  - Payment Help (₹30)
  - PDF Related (₹15)
- **Total amount is calculated automatically**
- Enter your payment reference number (UPI ID or Transaction ID)
- (Optional) Upload payment screenshot
- Add any special notes
- Click **Submit Service Request**

### 5. **Track Your Requests**
- Go to **My Requests** in your dashboard
- See all your submitted requests
- View status of each request:
  - **Pending**: Waiting for admin review
  - **Accepted**: Payment received, work in progress
  - **Processing**: Work is being done
  - **Completed**: Work is done
  - **Rejected**: Please contact the cyber café

### 6. **Logout**
- Click **Logout** in the navbar
- You'll be logged out and redirected to home

---

## 🔐 Admin Portal Guide

### 1. **Admin Login**
- Click **Login** → **Admin Login**
- Use demo credentials:
  - **Email**: admin@cyberserve.com
  - **Password**: admin123
- Click **Admin Login**

### 2. **Admin Dashboard**
You'll see:
- **Statistics**: Total requests, pending, accepted, completed
- **Filter Options**: Filter requests by status
- **Request Table**: All user service requests

### 3. **Manage Requests**

#### For Pending Requests:
- Click **Accept** to accept the request
  - Status changes to "Accepted"
  - User sees: "Accepted – Payment Received, work in progress"
- Click **Reject** to reject the request
  - Status changes to "Rejected"
  - User sees: "Rejected – Please contact the cyber café"

#### For Accepted Requests:
- Click **Complete** to mark as done
  - Status changes to "Completed"
  - User sees: "Completed"

### 4. **View Request Details**
In the table, you can see:
- Request ID
- User Name and ID
- Contact Number
- Services Selected
- Total Amount
- Payment Reference
- Current Status

---

## 📞 Contact Portal

### Send a Message
- Click **Contact** in the navbar
- Fill in your details:
  - Name
  - Email
  - Phone (optional)
  - Subject
  - Message
- Click **Send Message**
- You'll receive a confirmation message

### View Contact Info
- Phone: +91 98765 43210
- Email: support@cyberserve.com
- Address: CyberServe Center, Main Street
- Working Hours: 9:00 AM - 9:00 PM

---

## 🧪 Test Scenarios

### Scenario 1: Complete User Journey
1. Sign up as a new user
2. Login to your account
3. Create a service request (select 2-3 services)
4. Go to admin portal and accept the request
5. Check your dashboard to see updated status

### Scenario 2: Admin Management
1. Login as admin
2. View all pending requests
3. Accept some requests
4. Mark some as completed
5. Reject some requests
6. Check statistics

### Scenario 3: Multiple Services
1. Create a request with multiple services
2. Verify total amount is calculated correctly
3. Admin accepts the request
4. Check status updates in user dashboard

---

## 💡 Tips & Tricks

### For Users:
- ✅ Your User ID is unique and auto-generated
- ✅ You can create multiple service requests
- ✅ Total amount updates automatically when you select services
- ✅ Payment reference is required to submit a request
- ✅ Check your requests regularly for status updates

### For Admin:
- ✅ Use filters to quickly find requests by status
- ✅ Statistics update in real-time
- ✅ You can accept/reject multiple requests
- ✅ Once accepted, you can mark as completed
- ✅ Each action is logged with timestamp

---

## 🔄 Data Flow

```
User Signup
    ↓
User Login
    ↓
Create Service Request
    ↓
Submit to Admin
    ↓
Admin Reviews (Pending)
    ↓
Admin Accepts/Rejects
    ↓
If Accepted: Work in Progress
    ↓
Admin Marks Complete
    ↓
User Sees Completed Status
```

---

## 📱 Mobile Access

- The website is fully responsive
- All features work on mobile devices
- Hamburger menu appears on small screens
- Touch-friendly buttons and forms

---

## 🐛 Troubleshooting

### Issue: Can't login
- **Solution**: Check if you've created an account first
- **Solution**: Verify email and password are correct

### Issue: Service request not submitted
- **Solution**: Make sure you've selected at least one service
- **Solution**: Enter a valid payment reference number

### Issue: Admin can't see requests
- **Solution**: Make sure you're logged in as admin
- **Solution**: Check if any requests have been submitted by users

### Issue: Data not saving
- **Solution**: Check if browser allows localStorage
- **Solution**: Clear browser cache and try again

---

## 📊 Demo Data

### Pre-loaded Admin Account:
```
Email: admin@cyberserve.com
Password: admin123
Name: CyberServe Admin
Mobile: 9876543210
Address: CyberServe Center, Main Street
Timing: 9:00 AM - 9:00 PM
```

### Sample User (Create yourself):
```
Name: John Doe
Email: john@example.com
Mobile: 9876543210
Address: 123 Main Street, City
Password: password123
```

---

## 🎓 Learning Resources

This project demonstrates:
- ✅ HTML5 semantic structure
- ✅ CSS3 responsive design
- ✅ JavaScript DOM manipulation
- ✅ LocalStorage for data persistence
- ✅ Form validation
- ✅ Event handling
- ✅ Responsive grid layouts
- ✅ Modern UI/UX patterns

---

## 📝 Notes

- This is a **frontend demo** using localStorage
- For production, integrate with a real backend (PHP, Node.js, Python)
- Use a proper database (MySQL, PostgreSQL, MongoDB)
- Implement proper authentication and security
- Add email notifications
- Integrate payment gateway

---

**Happy Using! 🎉**

For more information, visit the README.md file.
