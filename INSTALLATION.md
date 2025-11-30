# CyberServe - Installation & Setup Guide

## 📋 System Requirements

- **Web Server**: Apache/XAMPP (or any web server)
- **Browser**: Chrome, Firefox, Safari, Edge (latest versions)
- **Storage**: LocalStorage enabled in browser
- **JavaScript**: Must be enabled

## 🚀 Installation Steps

### Step 1: Extract Files

All files are already in:
```
c:\xampp\htdocs\CyberServeapp\
```

### Step 2: Start Web Server

1. **Open XAMPP Control Panel**
2. **Start Apache** (click Start button)
3. **Start MySQL** (optional, for future database integration)

### Step 3: Access the Website

Open your browser and navigate to:
```
http://localhost/CyberServeapp/
```

Or go directly to the welcome page:
```
http://localhost/CyberServeapp/START_HERE.html
```

## 📁 File Structure

```
CyberServeapp/
├── START_HERE.html              ← 👈 Start here first!
├── index.html                   ← Homepage
├── user_login.html              ← User login
├── user_signup.html             ← User registration
├── user_dashboard.html          ← User dashboard
├── service_request.html         ← Service request form
├── admin_login.html             ← Admin login
├── admin_dashboard.html         ← Admin dashboard
├── contact.html                 ← Contact page
├── logout.html                  ← Logout
├── style.css                    ← Main stylesheet
├── script.js                    ← JavaScript functionality
├── README.md                    ← Full documentation
├── QUICKSTART.md                ← Quick start guide
├── DATABASE_SCHEMA.md           ← Database schema for backend
├── FILES_SUMMARY.txt            ← Files overview
├── INSTALLATION.md              ← This file
└── (All files are in the root directory)
```

## 🎯 First Time Setup

### 1. Open START_HERE.html
```
http://localhost/CyberServeapp/START_HERE.html
```
This page has all quick links and instructions.

### 2. Create a User Account
- Click "Create User Account"
- Fill in your details
- Your User ID will be auto-generated

### 3. Login as User
- Use your credentials to login
- Explore the user dashboard

### 4. Login as Admin
- Use demo credentials:
  - Email: admin@cyberserve.com
  - Password: admin123
- Explore the admin dashboard

## ✅ Verification Checklist

- [ ] Apache is running
- [ ] Can access http://localhost/CyberServeapp/
- [ ] START_HERE.html loads correctly
- [ ] Can create a user account
- [ ] Can login as user
- [ ] Can login as admin
- [ ] Can create a service request
- [ ] Can view requests in admin dashboard
- [ ] Can accept/reject requests

## 🔧 Troubleshooting

### Issue: "Cannot find server"
**Solution**: 
- Make sure Apache is running
- Check URL: http://localhost/CyberServeapp/
- Verify files are in c:\xampp\htdocs\CyberServeapp\

### Issue: Page shows blank or broken
**Solution**:
- Clear browser cache (Ctrl+Shift+Delete)
- Hard refresh (Ctrl+F5)
- Check browser console for errors (F12)

### Issue: Data not saving
**Solution**:
- Check if LocalStorage is enabled
- Try incognito/private window
- Clear browser data and try again

### Issue: Admin login not working
**Solution**:
- Use exact credentials: admin@cyberserve.com / admin123
- Make sure you're on admin_login.html
- Check browser console for errors

### Issue: User signup fails
**Solution**:
- Make sure all fields are filled
- Mobile number must be 10 digits
- Password must be at least 6 characters
- Email must be valid format

## 📱 Browser Console

To check for errors:
1. Press **F12** to open Developer Tools
2. Go to **Console** tab
3. Check for any red error messages
4. Report errors if needed

## 🔐 Security Notes

**Important**: This is a demo application using LocalStorage.

For production:
- [ ] Implement backend authentication
- [ ] Use HTTPS/SSL
- [ ] Hash passwords properly
- [ ] Validate all inputs
- [ ] Use proper database
- [ ] Add CSRF protection
- [ ] Implement rate limiting

## 📊 Data Storage

All data is stored in browser LocalStorage:
- User accounts
- Admin accounts
- Service requests
- Contact messages

**Note**: Data will be cleared if you clear browser cache/cookies.

## 🌐 Network Access

### Local Access Only
Currently, the website is only accessible locally:
```
http://localhost/CyberServeapp/
http://127.0.0.1/CyberServeapp/
```

### For Network Access
To access from other computers:
1. Find your computer's IP address
2. Access via: http://YOUR_IP/CyberServeapp/
3. Make sure firewall allows port 80

## 📚 Documentation Files

- **README.md** - Complete project documentation
- **QUICKSTART.md** - Step-by-step user guide
- **DATABASE_SCHEMA.md** - Database structure for backend
- **FILES_SUMMARY.txt** - Overview of all files
- **INSTALLATION.md** - This file

## 🚀 Next Steps

1. **Explore the Website**
   - Create user accounts
   - Submit service requests
   - Test admin features

2. **Read Documentation**
   - Check QUICKSTART.md for detailed guide
   - Review DATABASE_SCHEMA.md for backend integration

3. **Plan Backend Integration**
   - Choose backend language (PHP, Node.js, Python)
   - Set up database (MySQL, PostgreSQL)
   - Create API endpoints

4. **Customize**
   - Update colors and branding
   - Add your logo
   - Modify service list
   - Update contact information

## 💾 Backup Data

To backup your data:
1. Open browser DevTools (F12)
2. Go to Application → LocalStorage
3. Copy the data
4. Save to a file

## 🔄 Reset Data

To clear all data:
1. Open browser DevTools (F12)
2. Go to Application → LocalStorage
3. Delete all entries
4. Refresh the page

## 📞 Support

For issues or questions:
- Check QUICKSTART.md
- Review README.md
- Check browser console for errors
- Verify all files are in correct location

## 🎓 Learning Path

1. **Beginner**: Explore the website, create accounts, submit requests
2. **Intermediate**: Understand the code structure, modify CSS
3. **Advanced**: Integrate with backend, add new features

## 📝 Customization Guide

### Change Colors
Edit `style.css`:
```css
/* Change primary color from purple to blue */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
/* to */
background: linear-gradient(135deg, #0066cc 0%, #0099ff 100%);
```

### Add New Services
Edit `service_request.html`:
```html
<div class="checkbox-item">
    <input type="checkbox" id="newservice" name="services" value="new_service">
    <label for="newservice">New Service (₹XX)</label>
</div>
```

### Update Contact Info
Edit `contact.html`:
```html
<p>Your New Phone: +91 XXXXXXXXXX</p>
```

## ✨ Features Checklist

- [x] Homepage with navbar
- [x] Hero section with background
- [x] Services showcase
- [x] Charges display
- [x] User signup/login
- [x] User dashboard
- [x] Service request form
- [x] Real-time price calculation
- [x] Admin dashboard
- [x] Request management
- [x] Contact form
- [x] Responsive design
- [x] Status tracking
- [x] LocalStorage data management

## 🎉 You're All Set!

Everything is ready to use. Start by opening:
```
http://localhost/CyberServeapp/START_HERE.html
```

Enjoy! 🚀
