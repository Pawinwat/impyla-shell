# impyla-shell

**impyla-shell** is a Python-based tool that allows you to interact with Impala using a configurable shell environment. It requires Impala credentials and configuration details to connect to the database.

## Requirements

- Python 3.8 or higher
- Impala server access with the required credentials

## Installation

1. **Clone the repository**  
   First, clone the repository to your local machine:

   ```bash
   git clone https://github.com/your-username/impyla-shell.git
   cd impyla-shell
   ```

2. **Edit the configuration file**  
   Edit the `impyla-config.ini` file to include your Impala server details.

   Open the `impyla-config.ini` and update the following fields:

   ```ini
   [impala]
   host = your_impala_host
   port = your_impala_port
   database = your_impala_database
   username = your_impala_username
   password = your_impala_password
   realm = your_impala_realm
   ```

   - `host`: The Impala host address (e.g., `impala.yourcompany.com`).
   - `port`: The port number used to connect to Impala (e.g., `21050`).
   - `database`: The database you want to connect to.
   - `username`: Your Impala username.
   - `password`: Your Impala password.
   - `realm`: The Kerberos realm for authentication (if using Kerberos).

3. **Install dependencies**  
   The required dependencies are listed in `requirements.txt`. Install them using `pip`:

   ```bash
   python3 -m venv venv   # Create a virtual environment (optional but recommended)
   source venv/bin/activate  # Activate the virtual environment
   pip install -r requirements.txt
   ```

4. **Run the setup script**  
   After configuring the `impyla-config.ini` and installing the dependencies, run the `setup.sh` script to complete the installation:

   ```bash
   bash setup.sh
   ```

   This script sets up the environment and ensures everything is configured correctly.

## Usage

Once the setup is complete, you can start using `impyla-shell`.

1. Ensure that your virtual environment is activated (if you created one):

   ```bash
   source venv/bin/activate
   ```

2. Run the `impyla-shell` script:

   ```bash
   impyla-shell
   ```

3. The script will execute an Impala query. You can provide the query in two ways:

   - **From a file**: If you have a file containing your query, use the `-f` option:

     ```bash
     impyla-shell -f your_query_file.sql
     ```

   - **Directly as a string**: If you prefer to enter the query directly in the command line, use the `-q` option:

     ```bash
     impyla-shell -q "SELECT * FROM your_table LIMIT 10;"
     ```

4. **Kerberos Authentication (Optional)**: If your Impala instance uses Kerberos authentication, you can enable it using the `--kerberos` option:

   ```bash
   impyla-shell -q "SELECT * FROM your_table LIMIT 10;" --kerberos
   ```

## Configuration

- The `impyla-config.ini` file contains all the connection parameters to Impala. Ensure that this file is configured correctly before running the script.
- If using Kerberos authentication, make sure your environment is set up with the appropriate Kerberos credentials and realm.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to fork this repository, submit pull requests, and suggest improvements!
