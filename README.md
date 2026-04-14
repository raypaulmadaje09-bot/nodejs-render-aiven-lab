# Node.js Render Aiven Lab

This is a Node.js web application that connects to an Aiven MySQL database and is deployed using Render.

## Project Overview

This lab demonstrates:
- Creating a GitHub repository for a Node.js application
- Connecting to an Aiven MySQL database
- Deploying to Render platform
- Testing the deployment

## Prerequisites

- Node.js installed locally
- GitHub account
- Render account (https://render.com)
- Aiven account (https://aiven.io)

## Project Structure

```
nodejs-render-aiven-lab/
├── app.js              # Main Express application
├── package.json        # Project dependencies and scripts
├── .env.example        # Example environment variables
├── .gitignore         # Git ignore file
└── README.md          # This file
```

## Local Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/nodejs-render-aiven-lab.git
   cd nodejs-render-aiven-lab
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Set up environment variables:**
   - Copy `.env.example` to `.env`:
     ```bash
     cp .env.example .env
     ```
   - Fill in your Aiven MySQL credentials in `.env`

4. **Run locally:**
   ```bash
   npm start
   ```
   - Server will run at `http://localhost:3000`

## Aiven MySQL Setup

1. Login to https://aiven.io
2. Create a new MySQL service
3. Copy these credentials to your `.env` file:
   - Hostname
   - Username
   - Password
   - Port
   - Database Name

## Render Deployment

1. Login to https://render.com
2. Click "New +" → "Web Service"
3. Connect your GitHub repository
4. Configure:
   - **Runtime:** Node
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
5. Add environment variables in Render dashboard matching those in `.env.example`
6. Click "Create Web Service"

## Testing the Deployment

1. Wait for deployment to complete
2. Visit your Render URL (format: `https://app-name.onrender.com`)
3. You should see: "Database Connected Successfully: [timestamp]"
4. Test health endpoint: `https://app-name.onrender.com/health`

## Endpoints

- `GET /` - Tests database connection and returns current timestamp
- `GET /health` - Simple health check endpoint

## Troubleshooting

**Database Connection Failed:**
- Verify credentials in Render environment variables
- Check that Aiven database is running
- Ensure IP whitelist is configured in Aiven (or allow all IPs for testing)

**Server not starting:**
- Check that `npm install` completed successfully
- Verify `NODE_ENV` is set correctly
- Check Render logs for errors

## Resources

- [Express.js Documentation](https://expressjs.com/)
- [MySQL2 Documentation](https://github.com/sidorares/node-mysql2)
- [Aiven Documentation](https://docs.aiven.io/)
- [Render Documentation](https://render.com/docs)

## Lab Submission

Submit the following:
1. GitHub repository link
2. Render deployment URL
3. Screenshot of successful database connection