# Crawler

A web crawler for collecting and processing data from specified sources.

## Table of Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Database Setup](#database-setup)
- [Contributing](#contributing)

## Installation

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Ensure you have Python 3.8+ installed on your system.

## Configuration

### Environment Variables

Create a `.env` file in the project root with the following variables:

```
DATABASE_HOST=localhost
DATABASE_USER=crawler_user
DATABASE_PASSWORD=your_password
DATABASE_NAME=crawler_db
```

Update these values according to your local environment.

## Usage

Run the crawler with:

```bash
python crawler.py
```

Optional flags:
- `--verbose`: Enable detailed logging output
- `--limit N`: Limit crawling to N pages
- `--timeout S`: Set request timeout to S seconds

## Database Setup

### MySQL Configuration

The crawler uses MySQL to store collected data. Follow these steps to set up your database:

1. **Install MySQL**: Download and install from [MySQL Official Website](https://dev.mysql.com/downloads/mysql/)

2. **Create Database and User**:
   ```sql
   CREATE DATABASE crawler_db;
   CREATE USER 'crawler_user'@'localhost' IDENTIFIED BY 'your_password';
   GRANT ALL PRIVILEGES ON crawler_db.* TO 'crawler_user'@'localhost';
   FLUSH PRIVILEGES;
   ```

3. **Initialize Tables**: Run the database migration script:
   ```bash
   python scripts/init_db.py
   ```

### Connection Details

- **Host**: localhost (default)
- **Port**: 3306 (default MySQL port)
- **User**: crawler_user
- **Database**: crawler_db

Update the connection parameters in your `.env` file if using different settings.

## Contributing

Please read CONTRIBUTING.md for details on our code of conduct and the process for submitting pull requests.