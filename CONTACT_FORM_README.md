# Contact Form Setup Instructions

## How It Works

The contact form on `contact.html` uses **FormSubmit** - a free form backend service that sends form submissions directly to your email without needing a server.

## Current Configuration

- **Email Recipient**: s.a.ali-2@student.tudelft.nl
- **Service**: FormSubmit (https://formsubmit.co)
- **Form Location**: contact.html
- **Thank You Page**: thank-you.html

## Features

✅ **Email Notifications**: All form submissions are automatically sent to s.a.ali-2@student.tudelft.nl
✅ **No Server Required**: Works with static hosting (GitHub Pages, Netlify, etc.)
✅ **Spam Protection**: Honeypot field included to prevent bot submissions
✅ **Form Validation**: Required fields enforced
✅ **User Feedback**: Redirects to thank-you page after submission
✅ **Data Backup**: Submissions also stored in browser localStorage
✅ **Analytics Tracking**: Google Analytics event tracking included

## First-Time Setup

### Important: Email Verification

**The FIRST time someone submits the form, FormSubmit will:**
1. Send a verification email to s.a.ali-2@student.tudelft.nl
2. You MUST click the verification link in that email
3. After verification, all future submissions will be sent automatically

**Steps for first-time verification:**
1. Fill out and submit the contact form
2. Check the email inbox for s.a.ali-2@student.tudelft.nl
3. Look for an email from FormSubmit
4. Click the verification link
5. Done! All future submissions will work automatically

## What Gets Sent

Each form submission includes:
- **Full Name**: The person's complete name
- **Email**: Their email address
- **Phone Number**: Optional phone number
- **Message**: Optional message content
- **Submission Time**: Automatically added by FormSubmit

The email will be formatted as a nice HTML table for easy reading.

## For Local Testing

When testing locally (file:// protocol):
- FormSubmit will show their default success page instead of your custom thank-you page
- Emails will still be sent to s.a.ali-2@student.tudelft.nl (after verification)
- This is a FormSubmit limitation with local files

## For Production/Live Deployment

When deploying to a web server, update the redirect URL in `contact.html`:

**Find this line (around line 387):**
```html
<input type="hidden" name="_next" value="thank-you.html">
```

**Change to your full domain URL:**
```html
<input type="hidden" name="_next" value="https://yourdomain.com/thank-you.html">
```

Replace `yourdomain.com` with your actual domain.

## Troubleshooting

### Form doesn't send emails
1. Check if you verified the email address (see First-Time Setup above)
2. Check spam/junk folder for FormSubmit emails
3. Verify the email address in the form action is correct: `s.a.ali-2@student.tudelft.nl`

### Thank you page doesn't load
- This is normal for local testing (file:// URLs)
- Deploy to a web server (GitHub Pages, Netlify, etc.) for full functionality
- Update the `_next` value to full URL when deployed

### Receiving spam submissions
- The honeypot field (`_honey`) helps prevent bots
- FormSubmit has built-in spam filtering
- You can add CAPTCHA by changing `_captcha` to "true" in contact.html (line 385)

## Files Involved

- `contact.html` - The contact form page
- `thank-you.html` - Success page after form submission
- This README file for documentation

## Viewing Submissions

Submissions are sent to: **s.a.ali-2@student.tudelft.nl**

Additionally, submissions are stored in browser localStorage for backup:
1. Open browser Developer Tools (F12)
2. Go to "Application" or "Storage" tab
3. Click "Local Storage"
4. Look for key: `contactSubmissions`

## Need Help?

- FormSubmit Documentation: https://formsubmit.co
- FormSubmit Support: https://formsubmit.co/help

## Alternative: Change Email Address

To send submissions to a different email:

1. Open `contact.html`
2. Find line ~381: `<form action="https://formsubmit.co/s.a.ali-2@student.tudelft.nl"`
3. Replace email with new address
4. Save file
5. Submit test form to verify new email (FormSubmit will send verification)

---

**Last Updated**: November 2024
**Service**: FormSubmit (Free Forever)

