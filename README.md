# The Clover Studio

A small static website for The Clover Studio, a handmade flower studio based in Dhaka, Bangladesh.

## Preview locally

Open `index.html` in a browser. The site uses relative image paths, so the product photos should stay alongside the page.

## Publish with GitHub Pages

1. Create a new GitHub repository named `the-clover-studio`. Leave the options to add a README, license, or `.gitignore` unchecked.
2. In this folder, initialize Git and push the site:

   ```powershell
   git init -b main
   git add .
   git commit -m "Prepare Clover Studio website"
   git remote add origin https://github.com/YOUR-USERNAME/the-clover-studio.git
   git push -u origin main
   ```

3. In the repository, open **Settings > Pages** and choose **GitHub Actions** as the build and deployment source.
4. The included workflow deploys the site after each push to `main`. GitHub will show the published URL under **Settings > Pages**.

Replace `YOUR-USERNAME` in the remote URL with your GitHub username.