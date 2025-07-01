# devops-app

Project Overview
 DevOps App 
 
 A simple Node.js + Express app designed to demonstrate end-to-end DevOps practices including planning, CI/CD,
 Docker containerization, testing, and deployment on Render.
 
 This project was built as part of a DevOps learning module to simulate the lifecycle of a modern web application.
 Features- RESTful API (single route '/')- Message: Hello, DevOps!- Linting with ESLint- Unit tests with Jest and Supertest- Dockerized- Continuous Integration (CI)- Continuous Deployment (CD)

 
 Architecture
 User -> Render (Live App) -> Node.js Server -> Response: 'Hello, DevOps!'
                        [GitHub Push triggers Build via Docker]


                        
 Getting Started (Local)
 1. Clone the repo
   git clone https://github.com/gumutonii/devops-app.git

   cd devops-app
 3. Install dependencies
   npm install
   
 4. Run locally
   npm start
 Visit: http://localhost:3000
 Available Scripts- npm start: Start the app on port 3000- npm test: Run unit tests with Jest- npm run lint: Run ESLint to check code style
 CI/CD Pipeline

 This app uses GitHub Actions to:- Automatically lint and test on every Pull Request- Enforce code quality before merging- Trigger Docker-based deployment on main branch
DevOps App - Project Report
 Branch Protection Rules:- Require pull request- Require one review- Require CI checks to pass.

 
 Docker Setup
 
 Dockerfile includes:
 
 FROM node:18
 WORKDIR /app
 COPY package*.json ./
 RUN npm install
 COPY . .
 EXPOSE 3000
 CMD ["npm", "start"]
 Build the image:
  docker build -t devops-app .
 Run the container:
  docker run -p 3000:3000 devops-app
  
 Deployment
 
 Platform: Render.com
 Steps:
 1. Connected GitHub repository to Render
 2. Selected Docker environment
 3. Configured port and branch
 4. Enabled auto-deploy from 'main'
    
 Live Demo
 https://devops-app1.onrender.com
 Expected output:
 Hello, DevOps!


