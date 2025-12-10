# Legal Documents - Hosting Instructions

## 📄 Overview

This folder contains the legal documents required for ViDi Wallet's App Store and Google Play Store submissions:

- **PRIVACY_POLICY.md** - Privacy Policy (GDPR & CCPA compliant)
- **TERMS_OF_SERVICE.md** - Terms of Service (subscription terms, refund policy)

---

## 🚨 CRITICAL: Before Production

**These documents MUST be publicly accessible via web URLs before submitting to app stores.**

### Required Actions:

1. **Host the documents** on a publicly accessible website
2. **Update the URLs** in the app code (see below)
3. **Test the links** from the app settings page
4. **Add URLs to store listings** (App Store Connect & Google Play Console)

---

## 🌐 Hosting Options

### Option 1: GitHub Pages (Free, Recommended for MVP)

**Steps:**
1. Create a new repository: `vidi-wallet-legal` (public)
2. Add `PRIVACY_POLICY.md` and `TERMS_OF_SERVICE.md` to the repo
3. Enable GitHub Pages in repo settings
4. Access URLs will be:
   - Privacy Policy: `https://your-username.github.io/vidi-wallet-legal/PRIVACY_POLICY`
   - Terms of Service: `https://your-username.github.io/vidi-wallet-legal/TERMS_OF_SERVICE`

**Pros:**
- Free hosting
- Easy to update (just push changes to repo)
- Good for MVP and early production

**Cons:**
- Limited customization
- Branded with GitHub domain

---

### Option 2: Custom Domain Website (Professional, Recommended for Production)

**Steps:**
1. Purchase domain: `vidi-wallet.com` (or similar)
2. Set up a simple static website using:
   - **Netlify** (free tier available, easy deployment)
   - **Vercel** (free tier available, great for static sites)
   - **AWS S3 + CloudFront** (scalable, professional)
3. Upload HTML versions of the legal documents
4. Access URLs will be:
   - Privacy Policy: `https://vidi-wallet.com/privacy`
   - Terms of Service: `https://vidi-wallet.com/terms`

**Pros:**
- Professional appearance
- Full control over branding and domain
- Better for SEO and user trust

**Cons:**
- Domain registration cost (~$10-15/year)
- Requires basic web hosting setup

---

### Option 3: Convert to Web Pages (Recommended Approach)

**Create simple HTML pages from the markdown documents:**

1. Convert `PRIVACY_POLICY.md` to `privacy.html`
2. Convert `TERMS_OF_SERVICE.md` to `terms.html`
3. Host on any static web hosting service

**Sample HTML Template:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ViDi Wallet - Privacy Policy</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            color: #333;
        }
        h1 { color: #2c3e50; border-bottom: 2px solid #3498db; padding-bottom: 10px; }
        h2 { color: #34495e; margin-top: 30px; }
        a { color: #3498db; text-decoration: none; }
        a:hover { text-decoration: underline; }
    </style>
</head>
<body>
    <!-- Insert converted markdown content here -->
</body>
</html>
```

**Tools to Convert Markdown to HTML:**
- Online: https://markdowntohtml.com/
- CLI: `pandoc PRIVACY_POLICY.md -o privacy.html`
- VS Code Extension: "Markdown Preview Enhanced"

---

## 📝 Code Updates Required

After hosting the documents, update the following file:

### File: `lib/presentation/pages/settings/settings_page.dart`

**Line 772** - Privacy Policy URL:
```dart
const privacyPolicyUrl = 'https://vidi-wallet.com/privacy'; // Update this URL
```

**Line 809** - Terms of Service URL:
```dart
const termsOfServiceUrl = 'https://vidi-wallet.com/terms'; // Update this URL
```

**Replace with your actual hosted URLs.**

---

## 🏪 App Store Requirements

### iOS App Store Connect

**Privacy Policy URL:**
- Go to App Store Connect → Your App → App Information
- Scroll to "Privacy Policy URL"
- Enter: `https://vidi-wallet.com/privacy` (or your hosted URL)
- This field is **REQUIRED** for app submission

**Terms of Service (Optional but Recommended):**
- Can be linked in the app description
- Available via in-app settings (already implemented)

### Google Play Console

**Privacy Policy URL:**
- Go to Google Play Console → Your App → Store Presence → Privacy Policy
- Enter: `https://vidi-wallet.com/privacy` (or your hosted URL)
- This field is **REQUIRED** for apps that collect personal data

**Terms of Service (Optional but Recommended):**
- Can be linked in the app description
- Available via in-app settings (already implemented)

---

## ✅ Pre-Launch Checklist

Before submitting to app stores, verify:

- [ ] Privacy Policy is hosted and publicly accessible
- [ ] Terms of Service is hosted and publicly accessible
- [ ] URLs are updated in `settings_page.dart` (lines 772, 809)
- [ ] Links work from the app (test in Settings → Data & Privacy → Privacy Policy)
- [ ] Links work from the app (test in Settings → About → Terms of Service)
- [ ] Privacy Policy URL is added to App Store Connect
- [ ] Privacy Policy URL is added to Google Play Console
- [ ] Both documents include contact email: `support@vidi-wallet.com`
- [ ] Privacy Policy discloses all data collection (Firebase, Stripe, etc.)
- [ ] Terms of Service includes subscription pricing ($9.99 Basic, $19.99 Premium)
- [ ] Both documents are dated and include last updated date

---

## 📧 Contact Information in Documents

**Update the following placeholder contact information before hosting:**

### In PRIVACY_POLICY.md:
- Line 14: `support@vidi-wallet.com` - Update with actual support email
- Line 15: `https://vidi-wallet.com` - Update with actual website
- Line 16: `[Your Business Address]` - Add your actual business address

### In TERMS_OF_SERVICE.md:
- Line 225+: Update all email addresses (support@, legal@, disputes@, refunds@)
- Line 226: Update website URL
- Line 227: Add your actual business address

---

## 🔄 Updating Legal Documents

**Important:** Legal documents should be updated periodically and when:
- Privacy practices change (new data collection, third-party services)
- Subscription pricing changes
- Terms and conditions change
- Legal requirements change (new laws, regulations)

**Process for Updates:**
1. Update the markdown files in this folder
2. Convert to HTML (if using HTML hosting)
3. Upload new versions to hosting
4. Update "Last Updated" date in both documents
5. Notify users of material changes (required by law)
6. Keep old versions archived for legal compliance (7 years recommended)

---

## 📚 Additional Resources

### GDPR Compliance:
- https://gdpr.eu/privacy-notice/
- https://ico.org.uk/for-organisations/guide-to-data-protection/

### CCPA Compliance:
- https://oag.ca.gov/privacy/ccpa
- https://www.iubenda.com/en/help/5428-ccpa-compliance-guide

### App Store Guidelines:
- **Apple:** https://developer.apple.com/app-store/review/guidelines/#privacy
- **Google:** https://play.google.com/about/privacy-security-deception/

---

## 🚨 Legal Disclaimer

**These documents are templates and should be reviewed by a qualified attorney before publication.**

While we've made these documents comprehensive and compliant with GDPR and CCPA, they should be customized for your specific:
- Business structure and location
- Data collection practices
- Subscription terms
- Legal jurisdiction

**Consult with a lawyer specializing in:**
- Privacy law (GDPR, CCPA, etc.)
- Terms of Service contracts
- Consumer protection laws
- Subscription business regulations

---

## 📞 Questions?

If you have questions about hosting or legal documents, contact:
- **Development Team:** [Your Email]
- **Legal Counsel:** [Attorney Email]

---

**Last Updated:** November 27, 2025
**Next Review:** Before production deployment
