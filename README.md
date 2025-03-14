[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=18605320)
# WordPress Codespace Development Environment

A ready-to-use WordPress development environment that runs in GitHub Codespaces. Start developing for WordPress with just a single click - no local setup required!

## Features

- **Instant WordPress Setup**: WordPress is automatically installed and configured
- **Docker-based**: Uses Docker to isolate the WordPress and database environments
- **Task Buttons**: Convenient buttons in the status bar for common tasks
- **Enhanced Security**: Port is private by default and only made public when accessing the site
- **Persistent Storage**: Your changes persist between Codespace sessions
- **Stable Operation**: Improved task button reliability with robust error handling
- **Classroom Compatible**: Works seamlessly with GitHub Classroom for educational use
- **Git Integration**: Automatic Git sync check and easy submission with "Save to Github" button

## 🔒 Security Considerations

Avoid storing sensitive information in this environment as it's intended for development purposes only.

- Port 8080 is **private by default** - HOWEVER, the port is made public temporarily when you click the WP Home or WP Admin buttons so that you may view the web pages in your web browser. Anyone that has the URL to your codespace will be able to access it any time you are able to access it with your web browser. You cut off public access any time by going to the `Ports` tab and changing visibility from `Public` to `Private`.
- For additional security, consider changing the default admin password after setup



## Getting Started

### 1. Create a Codespace

Click the button below to create your own Codespace:

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=586814971&devcontainer_path=.devcontainer%2Fdevcontainer.json&location=WestEurope)

The setup process will:
- Install WordPress and configure the database
- Set up Apache to serve your WordPress site
- Configure port forwarding with private access by default
- Install necessary tools and extensions
- Configure Git settings for the environment

### 2. Access Your WordPress Site

Once the Codespace is ready, you can access your WordPress site using the status bar buttons:

- **WP Home**: Makes port 8080 public and opens the WordPress homepage
- **WP Admin**: Makes port 8080 public and opens the WordPress admin login page
- **PW Reset**: Resets the admin password if you're having trouble logging in
- **WP Restart**: Restarts the WordPress services and ensures port 8080 is private
- **Save to Github**: Commit and push your changes to GitHub with custom comments

### 3. WordPress Admin Credentials

Use these credentials to log in to the WordPress admin dashboard:

- **Username**: admin
- **Password**: password123
- **Email**: admin@example.com

## Development Workflow

### Accessing Your Site

Your WordPress site is accessible at:
```
https://<your-codespace-name>-8080.app.github.dev
```

The WordPress admin area is at:
```
https://<your-codespace-name>-8080.app.github.dev/wp-admin
```

**Important**: You must use the WP Home or WP Admin buttons to access these URLs, as they make the port public before opening the site.

### Making Changes

- WordPress files are located in the `/workspaces/<repository-name>/wordpress` directory
- You can install plugins and themes through the WordPress admin interface
- Changes to files are automatically reflected on your site

### Git Workflow

This environment includes enhanced Git functionality:

1. **Automatic Git Sync Check**: When you start your Codespace, it automatically checks for updates from GitHub
   - If updates are found, you'll be prompted to either replace your local code or keep your changes
   - This ensures you're always working with the latest code from your repository

2. **Save to Github Button**: Easily commit and push your changes
   - Click the "Save to Github" button in the status bar
   - Enter your submission comments when prompted
   - Your changes will be committed and pushed to GitHub
   - If a push fails, you'll have the option to force push (use with caution)

3. **Git Configuration**: Git is automatically configured with:
   - Default branch set to main
   - Pull configured to merge (not rebase)
   - User credentials set based on GitHub user information

### Troubleshooting

If you encounter any issues:

1. Use the **WP Restart** button in the status bar to restart WordPress
2. If you can't log in, use the **PW Reset** button
3. If you can't access your site, make sure you're using the WP Home or WP Admin buttons which handle port visibility
4. Check the log file at `/tmp/wp-task-log.txt` for diagnostic information about task button operations

## GitHub Classroom Compatibility

This environment is designed to work seamlessly with GitHub Classroom:

1. **Flexible Workspace Path**: The environment automatically adapts to the repository name assigned by GitHub Classroom
2. **No Hardcoded Paths**: All scripts use relative paths or environment variables to ensure compatibility
3. **Consistent Experience**: Students will have the same development experience regardless of repository name

## Behind the Scenes

This Codespace setup includes:

- WordPress with a MariaDB database
- Apache web server
- WP-CLI for command-line WordPress management
- Docker for containerization
- Task buttons for common operations
- Automatic port visibility management for security
- Git integration for code synchronization and submission

## Customization

You can customize this environment by:

- Editing `.devcontainer/devcontainer.json` to change Codespace settings
- Modifying `.devcontainer/docker-compose.yml` to adjust the Docker configuration
- Adding your own scripts to the `.devcontainer` directory

## Stopping and Restarting

When you stop and restart your Codespace, the WordPress services will automatically restart thanks to the `postStartCommand` in the devcontainer configuration. The port will remain private until you use the WP Home or WP Admin buttons.

---

Happy WordPress development!
