# Payload CMS Boilerplate with Next.js

A modern, full-stack boilerplate for building web applications with Payload CMS and Next.js. This template provides a solid foundation with authentication, media management, and a clean architecture ready for production.

## 🚀 Features

- **Payload CMS 3.0** - Headless CMS with powerful admin interface
- **Next.js 15** - React framework with App Router
- **TypeScript** - Full type safety throughout the application
- **PostgreSQL Database** - Robust SQL database with migrations
- **Vercel Blob Storage** - Scalable file storage for media assets
- **Authentication** - Built-in user management and admin panel
- **Rich Text Editor** - Lexical-based rich text editing
- **API Routes** - REST and GraphQL APIs out of the box
- **Testing Suite** - Vitest for unit tests, Playwright for E2E tests
- **Docker Support** - Containerized development environment
- **ESLint & Prettier** - Code quality and formatting

## 📋 Prerequisites

- Node.js 18.20.2 or higher (recommended: 20.9.0+)
- PostgreSQL database (local or cloud)
- npm (comes with Node.js)

## 🛠️ Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/next.js_payload_boilerplate_code.git
   cd next.js_payload_boilerplate_code
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```

   Edit `.env` and add your database connection string and other required secrets:
   ```env
   POSTGRES_URL=your_postgres_connection_string
   PAYLOAD_SECRET=your_secret_key_here
   BLOB_READ_WRITE_TOKEN=your_blob_token_here
   ```

4. **Generate types and import map**
   ```bash
   npm run generate:types
   npm run generate:importmap
   ```

5. **Run database migrations**
   ```bash
   npm run payload migrate
   ```

6. **Start development server**
   ```bash
   npm run dev
   ```

7. **Open your browser**
   - App: http://localhost:3000
   - Admin panel: http://localhost:3000/admin

## 🏗️ Project Structure

```
├── src/
│   ├── app/                    # Next.js App Router
│   │   ├── (frontend)/         # Public pages
│   │   ├── (payload)/          # Payload admin routes
│   │   └── api/                # API routes
│   ├── collections/            # Payload collections
│   │   ├── Media.ts           # Media upload collection
│   │   └── Users.ts           # User authentication
│   ├── payload.config.ts      # Payload configuration
│   └── payload-types.ts       # Generated types
├── tests/                      # Test suites
│   ├── e2e/                   # End-to-end tests
│   └── int/                   # Integration tests
├── media/                      # Static media files
├── migrations/                 # Database migrations
└── docker-compose.yml          # Docker configuration
```

## 🧪 Testing

### Unit & Integration Tests
```bash
npm run test:int
```

### End-to-End Tests
```bash
npm run test:e2e
```

### All Tests
```bash
npm run test
```

## 🚀 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Add the following environment variables in Vercel:
   - `POSTGRES_URL`
   - `PAYLOAD_SECRET`
   - `BLOB_READ_WRITE_TOKEN`
4. Deploy!

### Manual Deployment

1. **Build the application**
   ```bash
   npm run build
   ```

2. **Run database migrations**
   ```bash
   npm run payload migrate
   ```

3. **Start the production server**
   ```bash
   npm start
   ```

## 🐳 Docker Development

For local development with Docker:

1. Update `POSTGRES_URL` in `.env` to:
   ```
   POSTGRES_URL=postgres://postgres@localhost:54320/your_db_name
   ```

2. Update `docker-compose.yml` to match your database name

3. Start the database:
   ```bash
   docker-compose up -d
   ```

4. Run the development server:
   ```bash
   npm run dev
   ```

## 📚 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint
- `npm run test` - Run all tests
- `npm run test:int` - Run integration tests
- `npm run test:e2e` - Run E2E tests
- `npm run payload migrate:create` - Create new migration
- `npm run payload migrate` - Run pending migrations
- `npm run generate:types` - Generate TypeScript types
- `npm run generate:importmap` - Generate import map

## 🔧 Configuration

### Payload CMS

Edit `src/payload.config.ts` to customize:
- Collections and fields
- Admin panel settings
- Authentication configuration
- Upload handling

### Next.js

Edit `next.config.mjs` for Next.js configuration:
- Build settings
- Environment variables
- Rewrites and redirects

### Database

This boilerplate uses PostgreSQL. For local development, you can:
- Use Docker (recommended)
- Install PostgreSQL locally
- Use a cloud provider (Neon, Supabase, etc.)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Run the test suite
6. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

- [Payload CMS Documentation](https://payloadcms.com/docs)
- [Next.js Documentation](https://nextjs.org/docs)
- [Discord Community](https://discord.com/invite/payload)

## 📝 Notes

- This boilerplate is configured for production use with proper security measures
- Database migrations are required for schema changes
- The admin panel is accessible at `/admin` after creating your first admin user
- File uploads are handled via Vercel Blob Storage by default
