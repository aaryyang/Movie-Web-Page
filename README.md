# Movies App - Movie Review System

A full-stack web application that allows users to browse popular movies and write, edit, and delete reviews. Built with vanilla JavaScript frontend and Node.js/Express backend with MongoDB.

> **This project was created following the FreeCodeCamp tutorial series on building a movie review application.**

## Features

- 🎬 Browse popular movies from The Movie Database (TMDB)
- 🔍 Search for specific movies
- ⭐ Add reviews for movies
- ✏️ Edit existing reviews
- 🗑️ Delete reviews
- 📱 Responsive design

## Tech Stack

**Frontend:**
- Vanilla JavaScript
- HTML5
- CSS3
- Fetch API for HTTP requests

**Backend:**
- Node.js
- Express.js
- MongoDB with MongoDB Driver
- CORS enabled

**External APIs:**
- The Movie Database (TMDB) API

**Development Environment:**
- Replit (online IDE)

## Project Structure

```
MOVIES-APP/
├── api/
│   ├── reviews.controller.js    # API logic for reviews
│   └── reviews.route.js         # Review routes
├── dao/
│   └── reviewsDAO.js           # Database access layer
├── .config/                    # Replit configuration
├── node_modules/               # Dependencies
├── .env                        # Environment variables (not tracked)
├── .gitignore                  # Git ignore rules
├── .replit                     # Replit configuration
├── replit.nix                  # Nix configuration for Replit
├── index.js                    # Server entry point
├── server.js                   # Express app setup
├── script.js                   # Frontend - Movie listing
├── movie.js                    # Frontend - Review management
├── index.html                  # Home page
├── movie.html                  # Review page
├── package.json                # Project dependencies
└── README.md                   # This file
```

## Setup Instructions

### For Replit Users (Recommended)

1. **Fork this Repl** or **Import from GitHub**
2. **Install dependencies** (Replit will do this automatically)
3. **Set up environment variables** in Replit's Secrets tab:
   - Key: `MONGO_USERNAME`, Value: `your_mongodb_username`
   - Key: `MONGO_PASSWORD`, Value: `your_mongodb_password`
4. **Update MongoDB Connection** in `index.js`:
   ```javascript
   const uri = `mongodb+srv://${mongo_username}:${mongo_password}@your-cluster.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0`
   ```
5. **Update TMDB API Key** in `script.js` with your own API key
6. **Click the Run button** - The server will start automatically on port 8000

### For Local Development

#### Prerequisites
- Node.js (v14 or higher)
- MongoDB Atlas account or local MongoDB instance
- TMDB API key

#### Steps
1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd MOVIES-APP
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   Create a `.env` file in the root directory:
   ```env
   MONGO_USERNAME=your_mongodb_username
   MONGO_PASSWORD=your_mongodb_password
   ```

4. **Update configuration files**
   - Update MongoDB URI in `index.js`
   - Update TMDB API key in `script.js`

5. **Start the server**
   ```bash
   npm start
   # or
   node index.js
   ```

## Usage

1. **View Movies**: The home page shows popular movies from TMDB
2. **Search Movies**: Use the search bar to find specific movies
3. **Add Reviews**: Click "reviews" on any movie to go to the review page
4. **Manage Reviews**: Add, edit, or delete reviews on the movie review page

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/v1/reviews/movie/:id` | Get all reviews for a movie |
| POST | `/api/v1/reviews/new` | Create a new review |
| GET | `/api/v1/reviews/:id` | Get a specific review |
| PUT | `/api/v1/reviews/:id` | Update a review |
| DELETE | `/api/v1/reviews/:id` | Delete a review |

## Database Schema

### Reviews Collection
```javascript
{
  _id: ObjectId,
  movieId: Number,        // TMDB movie ID
  user: String,           // Username
  review: String,         // Review content
  date: Date             // Auto-generated
}
```

## Replit Configuration

This project includes:
- **`.replit`**: Main configuration file for Replit
- **`replit.nix`**: Package management for Replit environment
- **Debugger support**: Built-in debugging capabilities
- **Port configuration**: Automatically maps internal port 8000 to external port 80

### Environment Variables in Replit
Instead of using a `.env` file, use Replit's Secrets feature:
1. Go to the "Secrets" tab in your Repl
2. Add your environment variables there
3. They'll be automatically available as `process.env` variables

## Learning Objectives (FreeCodeCamp)

This project teaches:
- ✅ Building RESTful APIs with Express.js
- ✅ MongoDB database operations and schema design
- ✅ Frontend-backend communication with Fetch API
- ✅ CRUD operations (Create, Read, Update, Delete)
- ✅ Asynchronous JavaScript with async/await
- ✅ Environment variables and security best practices
- ✅ Error handling in both frontend and backend
- ✅ Working with external APIs (TMDB)

## Common Issues & Solutions

### ESM Import Errors
If you see `ERR_REQUIRE_ESM` errors:
- Make sure you're using `import` statements instead of `require()`
- Ensure your `package.json` includes `"type": "module"`

### MongoDB Connection Issues
- Double-check your MongoDB URI and credentials
- Ensure your MongoDB cluster allows connections from all IPs (0.0.0.0/0) for Replit

### TMDB API Issues
- Make sure your API key is valid and properly formatted
- Check that you're not exceeding API rate limits

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Open a Pull Request

## Resources

- [FreeCodeCamp - Build a Movie Review App](https://www.freecodecamp.org/)
- [The Movie Database (TMDB) API Documentation](https://developers.themoviedb.org/3)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [Express.js Documentation](https://expressjs.com/)
- [Replit Documentation](https://docs.replit.com/)

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- **FreeCodeCamp** for the excellent tutorial and learning materials
- [The Movie Database (TMDB)](https://www.themoviedb.org/) for the movie data API
- MongoDB for the database solution
- Express.js for the web framework
- Replit for the online development environment

---

**Happy coding and learning! 🚀**

*This project is part of the FreeCodeCamp curriculum for learning full-stack web development.*