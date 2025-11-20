# Contact Form Testing Checklist

## ✅ Quick Test Steps

### 1. First Time Setup (REQUIRED)
- [ ] Open the website
- [ ] Navigate to Contact page
- [ ] Fill out the form with test data
- [ ] Click Submit
- [ ] Check email: s.a.ali-2@student.tudelft.nl
- [ ] Find verification email from FormSubmit
- [ ] Click the verification link
- [ ] ✅ Form is now activated!

### 2. Test Submission
- [ ] Fill out the form again
- [ ] Click Submit
- [ ] You should be redirected (or see FormSubmit's success page if testing locally)
- [ ] Check email: s.a.ali-2@student.tudelft.nl
- [ ] You should receive an email with the form data

### 3. What You'll Receive by Email

**Email Subject:** "New Contact Form Submission - Solar Saver"

**Email Content (formatted as table):**
- Full Name: [person's name]
- Email: [person's email]
- Phone Number: [phone if provided]
- Message: [message if provided]

## 📧 Email Configuration

**Recipient**: s.a.ali-2@student.tudelft.nl
**Service**: FormSubmit.co (Free)
**Form Page**: contact.html
**Success Page**: thank-you.html

## 🚀 Live Deployment Notes

When you deploy to a live server (not local files):

1. Update the redirect URL in contact.html
2. Find line ~389: `<input type="hidden" name="_next" value="thank-you.html">`
3. Change to: `<input type="hidden" name="_next" value="https://YOUR-DOMAIN.com/thank-you.html">`
4. Replace YOUR-DOMAIN.com with your actual website URL

## 🔒 Security Features

- ✅ Honeypot spam protection (_honey field)
- ✅ No CAPTCHA (can be enabled if needed)
- ✅ Required field validation
- ✅ Email format validation
- ✅ FormSubmit's built-in security

## 📊 Data Tracking

- Google Analytics: Form submissions tracked
- LocalStorage: Backup copy saved in browser
- Email: All submissions sent to s.a.ali-2@student.tudelft.nl

## ❓ Troubleshooting

**Not receiving emails?**
- Did you verify the email address? (First time only)
- Check spam/junk folder
- Wait a few minutes (can take 1-2 minutes)

**Thank you page not loading?**
- Normal for local testing (file:// URLs)
- Works properly when deployed to web server

**Want to test without verification?**
- You can use a temporary email service first
- Once working, change to final email and verify

## 📝 Form Fields

1. **Full Name** (Required)
   - Text input
   - Cannot be empty

2. **Email** (Required)
   - Email format validation
   - Cannot be empty

3. **Phone Number** (Optional)
   - Any phone format accepted
   - Can be left empty

4. **Message** (Optional)
   - Multi-line text area
   - Can be left empty

---

**Status**: ✅ Ready to use (requires email verification on first submission)
**Last Updated**: November 2024

