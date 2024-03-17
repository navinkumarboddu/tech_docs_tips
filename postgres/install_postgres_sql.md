# POSTGRESQL
<hr>

To install PostgreSQL and restore a database from a backup on Ubuntu, you can follow these steps:

##### Step 1: Install PostgreSQL

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```

##### Step 2: Start and enable PostgreSQL service

```bash
sudo systemctl start postgresql
sudo systemctl enable postgresql
```

##### Step 3: Create a new PostgreSQL user and database

```bash
sudo -u postgres createuser --interactive
# Follow the prompts to create a new user

sudo -u postgres createdb your_database_name
```

##### Step 4: Grant privileges to the new user

```bash
sudo -u postgres psql
```

Inside the PostgreSQL shell, run the following SQL commands:

```sql
ALTER USER your_username WITH ENCRYPTED PASSWORD 'your_password';
ALTER USER your_username WITH SUPERUSER;
ALTER DATABASE your_database_name OWNER TO your_username;
\q
```

##### Step 5: Restore from backup

Assuming you have a backup file (e.g., backup.sql), you can restore it using the following command:

```bash
sudo -u postgres psql -d your_database_name -f /path/to/backup.sql
```

Replace your_database_name with the name of your database and /path/to/backup.sql with the actual path to your backup file.

##### Step 6: Verify the restore

You can log in to the PostgreSQL shell to verify that the data has been restored:

```bash
sudo -u postgres psql -d your_database_name
```

Now, you should be connected to the PostgreSQL shell for your database. You can run SQL queries or commands to verify that your data has been successfully restored.

Remember to replace placeholders like your_database_name, your_username, your_password, and /path/to/backup.sql with your actual values.

<hr>

By default, PostgreSQL doesn't create a password for the postgres user during installation. To set a password for the postgres user, you can use the following steps:
##### Step 1: Switch to the postgres user:

```bash
sudo -u postgres psql
```

##### Step 2: Set the password for the postgres user:

```sql
\password postgres
```

##### Step 3: You will be prompted to enter the new password for the postgres user. After entering the password, press Enter.

   Exit the PostgreSQL prompt:

```sql
\q
```

Now, the postgres user has a password associated with it. Make sure to use the new password when needed.


-------------------------------------------------------------------------------------------

# Drop DB

To drop a complete database that was created using the createdb command, you can use the dropdb command. Here's the syntax:

```bash
sudo -u postgres dropdb your_database_name
```

Replace your_database_name with the name of the database you want to drop. This command will prompt you for confirmation before actually dropping the database.

Please be careful when using the dropdb command, as it permanently removes the specified database and all its data. Ensure that you have a backup of the database if needed before proceeding.

--------------------------------------------------------------------------------------------------------

# Login to DB

To log in to PostgreSQL as a different user with a specific password, you can use the psql command-line tool. Here's the general syntax:

```bash
psql -U <username> -d <database_name> -h <hostname> -p <port_number> -W

    <username>: The PostgreSQL username you want to log in as.
    <database_name>: The name of the PostgreSQL database you want to connect to.
    <hostname>: The host where the PostgreSQL server is running. Use localhost if it's on the same machine.
    <port_number>: The port number on which the PostgreSQL server is listening. The default is 5432.
    -W: This flag prompts you for the password.
```

Example:

```bash
psql -U myuser -d mydatabase -h localhost -p 5432 -W
```

Replace myuser, mydatabase, and other parameters with your actual PostgreSQL username, database name, and connection details.

After executing the command, you will be prompted to enter the password for the specified user.

Make sure you have the PostgreSQL command-line tools installed, and the PostgreSQL server is running. Adjust the parameters based on your specific setup.
