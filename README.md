
# React Landing Page

This project is a landing page created with React using Vite. It is designed to be deployed on GitHub Pages.

Table of Contents
Getting Started
Development
Build
Deployment
Project Structure
License

## Getting Started
To get started with this project, you'll need to have Node.js and npm installed on your machine.

## Clone the repository:

bash

git clone https://github.com/Mikemupararano/react-landing-page.git
cd react-landing-page

Install dependencies:

bash

npm install

## Development
To run the project locally:

bash

npm run dev
This will start a development server and you can view the application by navigating to http://localhost:3000 in your browser.

## Build
To build the project for production:

bash

npm run build
This will generate a dist directory containing the production build of your application.

## Deployment
GitHub Pages
To deploy your React landing page to GitHub Pages:

Install the gh-pages package:

bash

npm install --save-dev gh-pages
Update package.json:

Add the following homepage field:

json

"homepage": "https://Mikemupararano.github.io/react-landing-page"
Add the following predeploy and deploy scripts:

json

"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist"
}
Deploy the project:

bash

npm run deploy
This will build the project and deploy the contents of the dist directory to the gh-pages branch of your repository.

GitHub Actions (Optional)
You can also automate the deployment process using GitHub Actions. Create a file named deploy.yml in the .github/workflows directory with the following content:

yaml

name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Setup Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '16'

      - name: Install dependencies
        run: npm install

      - name: Build project
        run: npm run build

      - name: Deploy to GitHub Pages
        run: npm run deploy
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
This workflow will automatically build and deploy your project to GitHub Pages whenever you push changes to the main branch.
Here is a
## Project Structure
Here is an overview of the project's structure:
![A screenshot of the first page](./src/assets/landing-page-screenshot1.png)

![A screenshot of the first page](./src/assets/landing-page-screenshot2.png)

arduino

react-landing-page/
├── public/
│   └── index.html
├── src/
│   ├── assets/
│   ├── components/
│   ├── App.jsx
│   ├── main.jsx
│   └── styles/
├── .gitignore
├── index.html
├── package.json
├── README.md
└── vite.config.js

## Credits
I have used this resource: https://www.youtube.com/watch?v=GVjIflROwJ4&t=1s

## License
This project is licensed under the MIT License. See the LICENSE file for more details.
Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh
