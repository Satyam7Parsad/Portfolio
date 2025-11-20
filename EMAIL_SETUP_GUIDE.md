# Email System Setup Guide for Portfolio

This portfolio uses **EmailJS** to send emails directly from the contact form. Follow these steps to set it up:

## Step 1: Create an EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" and create a free account
3. Verify your email address

## Step 2: Add Email Service

1. In your EmailJS dashboard, go to **"Email Services"**
2. Click **"Add New Service"**
3. Choose your email provider (Gmail recommended)
4. Click **"Connect Account"** and sign in with your Gmail (satyamprasad553@gmail.com)
5. Copy the **Service ID** (it will look like: `service_xxxxxxx`)

## Step 3: Create Email Template

1. Go to **"Email Templates"** in the dashboard
2. Click **"Create New Template"**
3. Use this template structure:

**Subject:**
```
New Contact Form Message: {{subject}}
```

**Content:**
```
You have received a new message from your portfolio contact form.

Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio website contact form.
```

4. Save the template and copy the **Template ID** (it will look like: `template_xxxxxxx`)

## Step 4: Get Your Public Key

1. Go to **"Account"** in the top right menu
2. Find your **Public Key** (it will look like: `abcd1234xyz`)

## Step 5: Update Your Website

Open `/Users/imaging/portfolio-website/script.js` and replace these three values:

```javascript
// Line 93 - Replace YOUR_PUBLIC_KEY
emailjs.init("YOUR_PUBLIC_KEY");

// Line 119 - Replace YOUR_SERVICE_ID and YOUR_TEMPLATE_ID
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', formData)
```

**Replace with:**
```javascript
emailjs.init("your_actual_public_key_here");
emailjs.send('service_xxxxxxx', 'template_xxxxxxx', formData)
```

## Step 6: Test Your Form

1. Open your portfolio in a browser
2. Fill out the contact form
3. Submit the form
4. Check your email (satyamprasad553@gmail.com) for the message

## Free Tier Limits

EmailJS free tier includes:
- ✅ 200 emails per month
- ✅ Unlimited email templates
- ✅ No credit card required

## Troubleshooting

**If emails aren't sending:**
1. Check browser console for errors (F12 → Console)
2. Verify all three IDs are correct in script.js
3. Make sure your EmailJS account is verified
4. Check EmailJS dashboard for error logs

**Alternative Setup:**
If you prefer a backend solution, I can help you set up:
- Node.js + Nodemailer
- PHP mail function
- Firebase Functions
- Netlify Forms

## Need Help?

Contact EmailJS support: https://www.emailjs.com/docs/
