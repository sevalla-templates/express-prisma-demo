<div align="center">
  <a href="https://sevalla.com">
    <img src="https://github.com/user-attachments/assets/7e0847f3-26d8-45a5-80eb-45f36ae353e3" alt="Sevalla Logo" width="80" height="80">
  </a>
  <h3 align="center">Express.js + Prisma Example</h3>
  <p align="center">
    A simple Express.js application using Prisma ORM with PostgreSQL
    <br />
    <a href="https://sevalla.com">Deploy to Sevalla</a>
    ·
    <a href="https://sevalla.com/docs">Sevalla Documentation</a>
    ·
    <a href="https://prisma.io/docs">Prisma Documentation</a>
  </p>
</div>

## About This Project

This is a simple Express.js application that demonstrates how to use Prisma ORM with PostgreSQL. The application includes:

- **REST API**: Basic CRUD operations for managing data
- **Prisma Schema**: Database schema definition with migrations
- **Database Seeding**: Optional script to populate the database with sample data
- **Frontend**: Simple HTML interface for testing the API endpoints

## Project Structure

```
├── prisma/
│   ├── schema.prisma      # Database schema definition
│   ├── migrations/        # Database migration files
│   └── seed.js           # Database seeding script
├── src/
│   └── index.js          # Express.js server with API endpoints
├── public/
│   └── index.html        # Simple frontend for testing
├── package.json          # Dependencies and scripts
└── README.md            # This file
```

## Local Development

### Prerequisites

- Node.js (v16 or higher)
- PostgreSQL database
- npm or yarn

### Setup

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd example-prisma
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up the database**
   ```bash
   # Set your database URL
   export DATABASE_URL="postgresql://username:password@localhost:5432/your_database"
   
   # Run migrations
   npx prisma migrate dev
   
   # (Optional) Seed the database
   npx prisma db seed
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

The application will be available at `http://localhost:3000`

## Deploying to Sevalla

This project is designed to be easily deployed on Sevalla. Here's how to deploy it:

### Prerequisites

- A Sevalla account (comes with $50 in free credits)
- This repository pushed to GitHub

### Deployment Steps

1. **Create an app on Sevalla**
   - Go to your Sevalla dashboard
   - Click **Applications** → **Create an app**
   - Connect your GitHub repository
   - Choose your branch (usually `main`)
   - Set your app name and region
   - Choose pod size (start with 0.5 CPU / 1GB RAM)
   - Click **Create** (skip deploy for now)

2. **Set up the database**
   - Go to **Databases** → **Add database**
   - Select PostgreSQL
   - Configure database credentials
   - Choose the same region as your app
   - Click **Create**

3. **Connect app to database**
   - In your database settings, go to **Connected Applications**
   - Click **Add Connection**
   - Select your app
   - Enable "Add environment variables"
   - Set variable name to `DATABASE_URL`
   - Click **Add connection**

4. **Deploy**
   - Go back to your app's **Deployment** tab
   - Click **Deploy**

5. **Seed the database (optional)**
   - Once deployed, go to **Web Terminal**
   - Run: `npx prisma db seed`

### Environment Variables

The following environment variables are required:

- `DATABASE_URL`: PostgreSQL connection string (automatically set by Sevalla)

## API Endpoints

Once deployed, your API will be available at your Sevalla app URL:

- `GET /` - Welcome message
- `GET /api/items` - Get all items
- `POST /api/items` - Create a new item
- `GET /api/items/:id` - Get item by ID
- `PUT /api/items/:id` - Update item
- `DELETE /api/items/:id` - Delete item

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is open source and available under the [MIT License](LICENSE).
