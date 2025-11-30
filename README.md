# Prism AI - AWS Serverless Multi-Specialized Chatbot Platform

A complete serverless web application with specialized AI chatbots powered by Amazon Bedrock, built with Next.js frontend and AWS Lambda backend.

## Architecture

- **Frontend**: Next.js 14 with Tailwind CSS (Glassmorphism design)
- **Backend**: AWS Lambda + API Gateway
- **Database**: Amazon DynamoDB
- **AI**: Amazon Bedrock (Claude 3 Haiku)
- **Authentication**: JWT tokens

## Features

- 5 Specialized AI Assistants (Teacher, Engineer, Lawyer, Cook, Doctor)
- Domain-restricted responses with automatic redirection
- Glassmorphism UI design with bluish color palette
- Real-time chat with session management
- JWT authentication system
- Serverless architecture for scalability

## Quick Start

### Prerequisites
- Node.js 18+
- AWS CLI configured
- AWS SAM CLI installed

### Frontend Setup
```bash
npm install
npm run dev
```

### Backend Deployment
```bash
cd aws-backend
sam build
sam deploy --guided
```

### Environment Setup
1. Copy `.env.example` to `.env.local`
2. Update `NEXT_PUBLIC_API_URL` with your API Gateway URL from SAM deployment

## Deployment

### AWS Resources Created
- 2 DynamoDB Tables (Users, Chats)
- 2 Lambda Functions (Auth, Chat)
- API Gateway with CORS enabled
- IAM roles with minimal permissions

### Cost Optimization
- Pay-per-request DynamoDB billing
- Lambda functions with optimized memory
- Bedrock Claude 3 Haiku (most cost-effective model)

## Usage

1. Visit the deployed frontend URL
2. Sign up for a new account
3. Click the floating chat button
4. Select your desired AI specialist
5. Start chatting within that domain

Each AI specialist only responds to questions in their field and redirects users to the appropriate expert for other topics.

## File Structure

```
/PRISM-AI
├── app/                    # Next.js frontend
├── aws-backend/           # AWS Lambda functions
│   ├── functions/
│   │   ├── auth/         # Authentication Lambda
│   │   └── chat/         # Chat Lambda with Bedrock
│   └── template.yaml     # SAM template
├── .env.example
└── README.md
```