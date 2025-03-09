# DockerUbuntu

DOCKER + POSTGRES + pgADMIN.

PostgreSQL running in a Docker container on your Ubuntu 24.04 system.

### Step 1: Install Docker
1. Update your system:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. Install Docker:
   ```bash
   sudo apt install docker.io -y
   ```
3. Start and enable Docker:
   ```bash
   sudo systemctl start docker
   sudo systemctl enable docker
   ```
4. Verify Docker installation:
   ```bash
   docker --version
   ```

### Step 2: Pull the PostgreSQL Docker Image
1. Pull the official PostgreSQL image from Docker Hub:
   ```bash
   docker pull postgres
   ```

### Step 3: Run PostgreSQL in a Docker Container
1. Create and run a PostgreSQL container:
   ```bash
   docker run --name postgres-container -e POSTGRES_PASSWORD=yourpassword -d -p 5432:5432 postgres
   ```
   Replace `yourpassword` with a strong password for the PostgreSQL `postgres` user.

2. Verify the container is running:
   ```bash
   docker ps
   ```

### Step 4: Access PostgreSQL
1. Install `psql` (PostgreSQL client) on your Ubuntu system:
   ```bash
   sudo apt install postgresql-client -y
   ```
2. Connect to the PostgreSQL database:
   ```bash
   psql -h localhost -U postgres
   ```
   Enter the password you set earlier when prompted.

Let’s get pgAdmin set up on your Linux system step by step, Fabio. Here's how:

### Step 1: Update Your System
1. Open a terminal and update the package lists:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

### Step 2: Install pgAdmin
1. Add the pgAdmin repository:
   ```bash
   curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
   echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" | sudo tee /etc/apt/sources.list.d/pgadmin4.list
   ```
2. Install pgAdmin:
   ```bash
   sudo apt update
   sudo apt install pgadmin4 -y
   ```

### Step 3: Configure pgAdmin
1. Launch the setup to configure pgAdmin:
   ```bash
   sudo /usr/pgadmin4/bin/setup-web.sh
   ```
   During this setup, it will ask you to create a username and password. Make sure to remember them, as you’ll need them to log in.

### Step 4: Access pgAdmin
1. Open your web browser and navigate to `http://localhost/pgadmin4`.
2. Log in with the credentials you set up during the configuration.
