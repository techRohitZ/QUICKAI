# QUICKAI - AI-Powered Content Creation Platform

A comprehensive AI-powered platform that provides various content creation tools including article writing, image generation, background removal, and resume review services.

## 🚀 Features

### Content Creation
- **Article Writing**: Generate high-quality articles using AI
- **Blog Title Generation**: Create engaging blog titles for your content
- **Image Generation**: Generate AI-powered images from text prompts
- **Background Removal**: Remove backgrounds from images automatically
- **Object Removal**: Remove specific objects from images
- **Resume Review**: Get AI-powered feedback on your resume

### User Management
- **Authentication**: Secure user authentication with Clerk
- **Dashboard**: Track your creations and usage
- **Premium Plans**: Free tier with usage limits and premium subscription
- **Community**: Share and discover content with other users

## 🛠️ Tech Stack

### Frontend
- **React 19** - Modern React with latest features
- **Vite** - Fast build tool and development server
- **Tailwind CSS** - Utility-first CSS framework
- **React Router DOM** - Client-side routing
- **Clerk** - Authentication and user management
- **Axios** - HTTP client for API calls
- **React Markdown** - Markdown rendering
- **Lucide React** - Beautiful icons

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **Clerk Express** - Authentication middleware
- **Neon Database** - Serverless PostgreSQL database
- **Cloudinary** - Image and video management
- **OpenAI API** - AI content generation
- **Clipdrop API** - Image generation and editing
- **Multer** - File upload handling

## 📁 Project Structure

```
QUICKAI/
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/         # Application pages
│   │   ├── assets/        # Static assets
│   │   └── App.jsx        # Main application component
│   ├── package.json
│   └── vite.config.js
├── server/                 # Backend Node.js application
│   ├── controllers/       # Business logic controllers
│   ├── routes/           # API route definitions
│   ├── middlewares/      # Custom middleware
│   ├── configs/          # Configuration files
│   ├── server.js         # Main server file
│   └── package.json
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn
- PostgreSQL database (Neon recommended)
- Clerk account for authentication
- Cloudinary account for image management
- OpenAI API key
- Clipdrop API key

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd QUICKAI
   ```

2. **Install dependencies**
   ```bash
   # Install client dependencies
   cd client
   npm install
   
   # Install server dependencies
   cd ../server
   npm install
   ```

3. **Environment Setup**
   
   Create `.env` files in both client and server directories:

   **Server `.env`:**
   ```env
   PORT=3000
   CLERK_SECRET_KEY=your_clerk_secret_key
   DATABASE_URL=your_neon_database_url
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   GEMINI_API_KEY=your_gemini_api_key
   CLIPDROP_API_KEY=your_clipdrop_api_key
   ```

   **Client `.env`:**
   ```env
   VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   VITE_BASE_URL=http://localhost:3000
   ```

4. **Database Setup**
   
   Create the following table in your PostgreSQL database:
   ```sql
   CREATE TABLE creations (
     id SERIAL PRIMARY KEY,
     user_id VARCHAR(255) NOT NULL,
     prompt TEXT NOT NULL,
     content TEXT NOT NULL,
     type VARCHAR(50) NOT NULL,
     publish BOOLEAN DEFAULT false,
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

### Running the Application

1. **Start the server**
   ```bash
   cd server
   npm start
   ```

2. **Start the client**
   ```bash
   cd client
   npm run dev
   ```

3. **Access the application**
   - Frontend: http://localhost:5173
   - Backend API: http://localhost:3000

## 📱 Usage

### Free Tier
- 10 free AI generations per month
- Access to article writing and blog title generation
- Basic dashboard functionality

### Premium Tier
- Unlimited AI generations
- Access to all features including:
  - Image generation
  - Background removal
  - Object removal
  - Resume review
- Priority support

## 🔧 API Endpoints

### Authentication
All endpoints require authentication via Clerk.

### AI Routes (`/api/ai`)
- `POST /generate-article` - Generate articles
- `POST /generate-blog-title` - Generate blog titles
- `POST /generate-image` - Generate images (Premium only)
- `POST /remove-background` - Remove image backgrounds (Premium only)
- `POST /remove-object` - Remove objects from images (Premium only)
- `POST /review-resume` - Review resume (Premium only)

### User Routes (`/api/user`)
- `GET /get-user-creations` - Get user's creation history

## 🚀 Deployment

### Vercel Deployment
Both client and server are configured for Vercel deployment with `vercel.json` files.

1. **Deploy Server**
   ```bash
   cd server
   vercel --prod
   ```

2. **Deploy Client**
   ```bash
   cd client
   vercel --prod
   ```

### Environment Variables for Production
Make sure to set all required environment variables in your deployment platform.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License.

## 🆘 Support

For support, email support@quickai.com or join our community discussions.

## 🔮 Roadmap

- [ ] Advanced AI models integration
- [ ] Batch processing capabilities
- [ ] API rate limiting improvements
- [ ] Mobile application
- [ ] Advanced analytics dashboard
- [ ] Team collaboration features

---

**QUICKAI** - Empowering creativity with AI 🚀

Live Link: https://quickai-drab.vercel.app/
