# URL Shortner
#### Project Structure
```
📦 URL Shortener
├── backend
│   ├── config
│   │   └── authConfig.js      # Configuration for authentication
│   ├── server.js              # Express server setup
│   ├── models
│   │   ├── Url.js             # Mongoose schema for URLs
│   │   └── User.js            # Mongoose schema for User authentication
│   └── routes
│       ├── urlRoutes.js       # API endpoints for shortening and redirecting URLs
│       └── userRoutes.js      # API endpoints for user authentication and link management
└── frontend
    ├── src
    │   ├── App.js             # Main React component
    │   └── components
    │       ├── Shortener.js   # Component for URL shortening form
    │       └── Dashboard.js   # User dashboard for managing URLs
    └── package.json           # Frontend dependencies
```
# URL Shortener with User Management and Analytics

A URL shortener application with added features for user management, URL expiration, and click analytics.

### New Features

1. **User Authentication for Personal Link Management**:
   - Users can register, log in, and manage their shortened URLs.
   - Each URL is linked to a specific user, providing personal link management.

2. **URL Expiration**:
   - URLs can be set to expire after a certain period.
   - Expired URLs automatically become inaccessible and display an error if accessed.

3. **Click Analytics**:
   - The application tracks the number of clicks on each shortened URL.
   - Users can view the click count in their dashboard for insights.


## Installation

After cloning and setting up the backend and frontend, configure user authentication by adding `authConfig.js` in the `config` folder of the backend:

```plaintext
SECRET_KEY=<your_secret_key>
```


## Updated API Endpoints

1. **User Authentication**
   - **POST /register** - Register a new user.
   - **POST /login** - Log in a user and retrieve a token.
  
2. **URL Management**
   - **POST /shorten** - Shorten a URL with optional expiration date.
   - **GET /urls** - Retrieve all URLs created by the logged-in user.
   - **GET /:shortCode** - Redirect to the original URL, update the click count if not expired.
   - **DELETE /:shortCode** - Delete a user’s URL.

3. **Analytics**
   - **GET /analytics/:shortCode** - View the click count for a specific shortened URL.
