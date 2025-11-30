# CyberServe - Online Cyber Cafe Website

A complete full-stack web application for managing online cyber cafe services with user and admin portals.

## 📋 Features

### 1. **Homepage**
- Clean navigation bar with menu items (Home, Services, Charges, Contact, Login)
- Hero section with background image and tagline
- Four service boxes (Form Fill, ID Card, Photo/Print, Govt Services)
- Services & Charges section with pricing details
- Responsive design for mobile, tablet, and desktop

### 2. **User System**
- **User Signup**: Name, Email, Password, Mobile, Address
- **User Login**: Email + Password authentication
- **Auto-generated User ID**: U1001, U1002, etc.
- **Logout**: Clear session and redirect to home

### 3. **User Portal**
- **Dashboard**: View profile, admin details, quick actions
- **Service Request Form**: 
  - Auto-filled user information
  - Multi-select services with pricing
  - Real-time total amount calculation
  - Payment reference number input
  - Optional payment screenshot upload
- **My Requests**: View all submitted requests with status
- **Status Tracking**: Pending, Accepted, Processing, Completed, Rejected

### 4. **Admin Portal**
- **Admin Login**: Email + Password (Demo: admin@cyberserve.com / admin123)
- **Admin Dashboard**:
  - View all service requests
  - Filter by status
  - Statistics (Total, Pending, Accepted, Completed)
  - Accept/Reject requests
  - Mark requests as completed
- **Request Management**: Full CRUD operations

### 5. **Contact Portal**
- Contact form with Name, Email, Message
- Contact information display
- Working hours and location details

### 6. **Services & Charges**
- Aadhaar Update - ₹50
- PAN Card Apply - ₹100
- Online Exam Form - ₹80
- Printout (per page) - ₹5
- Scan & Email - ₹20
- Voter ID Apply - ₹70
- Bank Seva (KYC) - ₹60
- Train Ticket Booking - ₹40
- Online Certificate Download - ₹50
- Device Related Work - ₹100
- Online Payment Help - ₹30
- PDF Related Work - ₹15

## 🗂️ Project Structure

```
CyberServeapp/
├── index.html              # Homepage
├── user_login.html         # User login page
├── user_signup.html        # User signup page
├── user_dashboard.html     # User dashboard
├── service_request.html    # Service request form
├── admin_login.html        # Admin login page
├── admin_dashboard.html    # Admin dashboard
├── contact.html            # Contact page
├── logout.html             # Logout page
├── style.css               # Main stylesheet
├── script.js               # JavaScript functionality
└── README.md               # This file
```

## 🚀 Getting Started

### Prerequisites
- Any modern web browser (Chrome, Firefox, Safari, Edge)
- No server-side setup required (uses localStorage for demo)

### Installation

1. **Extract the files** to your web server directory:
   ```
   c:\xampp\htdocs\CyberServeapp\
   ```

2. **Open in browser**:
   ```
   http://localhost/CyberServeapp/
   ```

## 👤 Demo Credentials

### User Account
- Create a new account using the signup form
- Example: 
  - Name: John Doe
  - Email: john@example.com
  - Mobile: 9876543210
  - Password: password123

### Admin Account
- **Email**: admin@cyberserve.com
- **Password**: admin123

## 📱 Responsive Design

The website is fully responsive and works perfectly on:
- **Desktop**: 1200px and above
- **Tablet**: 768px to 1199px
- **Mobile**: Below 768px

## 🎨 UI/UX Features

- Modern gradient design (Purple & Blue)
- Smooth animations and transitions
- Hamburger menu for mobile
- Dropdown navigation menus
- Status badges with color coding
- Form validation with error messages
- Toast notifications for user feedback
- Hover effects on interactive elements

## 💾 Data Storage

Currently uses **localStorage** for demo purposes:
- `cyberserve_users`: User accounts
- `cyberserve_admins`: Admin accounts
- `cyberserve_requests`: Service requests
- `cyberserve_contacts`: Contact messages
- `currentUser`: Active user session
- `currentAdmin`: Active admin session

## 🔄 Workflow

### User Workflow
1. Signup → Login → Dashboard → Create Service Request → Track Status

### Admin Workflow
1. Login → View Requests → Accept/Reject → Mark Complete

### Service Request Status Flow
```
Pending → Accepted → Processing → Completed
       ↘ Rejected
```

## 🎯 Key Functionalities

### User Features
- ✅ User registration with validation
- ✅ Secure login/logout
- ✅ View personal profile
- ✅ View admin contact details
- ✅ Create service requests
- ✅ Real-time price calculation
- ✅ Track request status
- ✅ Payment reference tracking

### Admin Features
- ✅ Admin login
- ✅ View all service requests
- ✅ Filter requests by status
- ✅ Accept/Reject requests
- ✅ Mark requests as completed
- ✅ View request statistics
- ✅ View user details

## 🔐 Security Notes

**Important**: This is a demo application using localStorage. For production:
- Implement proper backend authentication (PHP, Node.js, Django, etc.)
- Use secure password hashing (bcrypt, argon2)
- Implement HTTPS/SSL
- Use proper database (MySQL, PostgreSQL)
- Add CSRF protection
- Implement rate limiting
- Add email verification
- Use environment variables for sensitive data

## 📞 Contact Information

For support or inquiries:
- Email: support@cyberserve.com
- Phone: +91 98765 43210
- Address: CyberServe Center, Main Street

## 📄 License

This project is open source and available for educational purposes.

## 🙏 Credits

Built with:
- HTML5
- CSS3
- JavaScript (Vanilla)
- Font Awesome Icons
- Unsplash Images

---

**Version**: 1.0.0  
**Last Updated**: December 2024
