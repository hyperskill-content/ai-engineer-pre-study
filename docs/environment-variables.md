# Environment Variables

The .env file stores environment-specific configuration and secrets that should never be committed to version control. They store sensitive data like API keys, database credentials, and feature flags.

Example `.env` file:

```
API_KEY=sk-1234567890abcdef
DATABASE_URL=postgresql://user:pass@localhost:5432/mydb
```

Always add `.env` to your `.gitignore` (especially if you decide to rename this file) and create a `.env.template` file (with dummy values) to show what variables are needed to run the app:

```
# .env.template
API_KEY=your_api_key_here
DATABASE_URL=your_database_url_here
DEBUG=False
```

Use `.env.development`, `.env.production` for different environments.
