# Setup Instructions for GitHub Pages

## Step 1: Create Public GitHub Repository

1. Go to https://github.com/new
2. Fill in the repository details:
   - **Repository name:** `ViDi-Wallet-Docs`
   - **Description:** `Legal documents and support documentation for ViDi Wallet`
   - **Visibility:** ✅ **Public** (required for free GitHub Pages)
   - **Initialize this repository with:** Leave ALL unchecked (we already have files)
3. Click **"Create repository"**

## Step 2: Push Local Repository to GitHub

Run these commands in your terminal:

```bash
cd "/Users/vaibhav.mahant/Desktop/Github & Code/Fun Projects/The Budget App/ViDi-Wallet-Docs"

# Add GitHub remote
git remote add origin https://github.com/vaibhav345/ViDi-Wallet-Docs.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 3: Enable GitHub Pages

1. Go to your repository: https://github.com/vaibhav345/ViDi-Wallet-Docs
2. Click **"Settings"** tab
3. In the left sidebar, click **"Pages"**
4. Under **"Build and deployment"**:
   - **Source:** Deploy from a branch
   - **Branch:** main
   - **Folder:** / (root)
5. Click **"Save"**

## Step 4: Wait for Deployment (2-5 minutes)

GitHub will build and deploy your site. You'll see:
- ✅ A green checkmark when ready
- Your site URL: `https://vaibhav345.github.io/ViDi-Wallet-Docs/`

## Step 5: Verify Your URLs

Once deployed, your legal documents will be accessible at:

- **Homepage:** https://vaibhav345.github.io/ViDi-Wallet-Docs/
- **Privacy Policy:** https://vaibhav345.github.io/ViDi-Wallet-Docs/legal/PRIVACY_POLICY
- **Terms of Service:** https://vaibhav345.github.io/ViDi-Wallet-Docs/legal/TERMS_OF_SERVICE
- **Help & Support:** https://vaibhav345.github.io/ViDi-Wallet-Docs/legal/README

## Step 6: Update App Links

After verifying the URLs work, the app code will be automatically updated with these URLs.

---

## Troubleshooting

### "Repository not found" error
- Make sure you created the repository as **public**
- Verify the repository name is exactly `ViDi-Wallet-Docs`

### "Permission denied" error
- Run: `git config --global credential.helper osxkeychain`
- Try pushing again

### Pages not deploying
- Check Settings → Pages for error messages
- Ensure repository is public
- Wait a few more minutes (first deploy can take 5-10 minutes)

### 404 errors on document links
- URLs are case-sensitive: Use `PRIVACY_POLICY` not `privacy_policy`
- Allow a few minutes for GitHub Pages to update after push

---

**Next:** After GitHub Pages is live and verified, proceed with updating the app links.
