# EC2 Setup Instructions

## 1. Connect to EC2 Instance via EC2 Instance Connect

## 2. Install Node Version Manager (nvm) and Node.js

- **Switch to superuser and install nvm:**

  ```sh
  sudo su -
  ```

  ```sh
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
  ```

- **Activate nvm:**

  ```sh
  . ~/.nvm/nvm.sh
  ```

- **Install the latest version of Node.js using nvm:**

  ```sh
  nvm install node
  ```

- **Verify that Node.js and npm are installed:**

  ```sh
  node -v
  ```

  ```sh
  npm -v
  ```

## 3. Install Git

- **Update the system and install Git:**

  ```sh
  sudo yum update -y
  ```

  ```sh
  sudo yum install git -y
  ```

- **Check Git version:**

  ```sh
  git --version
  ```

- **Clone your code repository from GitHub:**

  ```sh
  git clone [your-github-link]
  ```

- **Navigate to the directory and install packages:**

  ```sh
  cd real-estate-prod
  ```

  ```sh
  cd server
  ```

  ```sh
  npm i
  ```

- **Create Env File and Port 80:**

  ```sh
  echo "PORT=80" > .env
  ```

- **Start the application:**
  ```sh
  npm run dev
  ```

## 4. Install pm2 (Production Process Manager for Node.js)

- **Install pm2 globally:**

  ```sh
  npm i pm2 -g
  ```

- **Create a pm2 ecosystem configuration file (inside server directory):**

  ```js
  module.exports = {
    apps : [{
      name: 'inventory-management',
      script: 'npm',
      args: 'run dev',
      env: {
        NODE_ENV: 'development',
        ENV_VAR1: 'environment-variable',
      }
    }],
  };
  ```

- **Modify the ecosystem file if necessary:**

  ```sh
  nano ecosystem.config.js
  ```

- **Set pm2 to restart automatically on system reboot:**

  ```sh
  sudo env PATH=$PATH:$(which node) $(which pm2) startup systemd -u $USER --hp $(eval echo ~$USER)
  ```

- **Start the application using the pm2 ecosystem configuration:**

  ```sh
  pm2 start ecosystem.config.js
  ```

**Useful pm2 commands:**

- **Stop all processes:**

  ```sh
  pm2 stop all
  ```

- **Delete all processes:**

  ```sh
  pm2 delete all
  ```

- **Check status of processes:**

  ```sh
  pm2 status
  ```

- **Monitor processes:**
  ```sh
  pm2 monit