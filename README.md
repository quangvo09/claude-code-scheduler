# Claude Code Scheduler

A GitHub Actions workflow that automatically runs Claude AI to work on your codebase at scheduled intervals. This project allows you to set up continuous AI assistance for your development tasks without manual intervention.

## 🚀 Features

- **Automated Code Assistance**: Claude AI automatically works on your codebase at scheduled times
- **Flexible Scheduling**: Configurable cron schedule to run at your preferred intervals
- **Manual Trigger**: Ability to manually trigger the workflow when needed
- **Continuous Development**: Keep your project moving forward even when you're not actively coding

## 📋 Prerequisites

- A GitHub repository
- An Anthropic API key with access to Claude

## ⚙️ Setup

### 1. Fork or Clone This Repository

```bash
git clone https://github.com/yourusername/claude-code-scheduler.git
cd claude-code-scheduler
```

### 2. Configure Your Anthropic API Key

1. Go to your GitHub repository settings
2. Navigate to **Secrets and variables** → **Actions**
3. Add a new repository secret:
   - **Name**: `ANTHROPIC_API_KEY`
   - **Value**: Your Anthropic API key

### 3. Customize the Workflow

The workflow is configured in `.github/workflows/claude-scheduler.yml`. You can customize:

- **Schedule**: Modify the cron expression to change when the workflow runs
- **System Prompt**: Adjust the system prompt to match your coding style and preferences
- **User Prompt**: Modify the prompt to focus on specific tasks or areas of your codebase

### 4. Push to GitHub

```bash
git add .
git commit -m "Add Claude Code Scheduler workflow"
git push origin main
```

## ⏰ Schedule Configuration

The default schedule runs the workflow 4 times per day:
- 1:00 AM UTC
- 6:00 AM UTC  
- 11:00 AM UTC
- 4:00 PM UTC

To modify the schedule, edit the cron expression in `.github/workflows/claude-scheduler.yml`:

```yaml
on:
  schedule:
    - cron: '0 1,6,11,16 * * *' # Current schedule
```

## 🔧 Customization

### System Prompt

The system prompt defines Claude's role and behavior. You can modify it in the workflow file:

```yaml
system_prompt: "You are a helpful coding assistant."
```

### User Prompt

The user prompt tells Claude what to work on. The current prompt:

```yaml
prompt: |
  Continue working on what you were working on previously. If you weren't working on something previously, then come up with a list of tasks to work on based on what is left in the codebase.
```

You can customize this to:
- Focus on specific features or bugs
- Prioritize certain types of tasks
- Work on specific files or directories
- Follow your project's coding standards

## 🚀 Usage

### Automatic Execution

Once set up, the workflow will run automatically according to the schedule. Claude will:
1. Analyze your codebase
2. Identify tasks to work on
3. Make commits with improvements
4. Create pull requests for review

### Manual Execution

You can manually trigger the workflow:
1. Go to your GitHub repository
2. Click on the **Actions** tab
3. Select the **Run Claude Code Prompt** workflow
4. Click **Run workflow**

## 📁 Project Structure

```
claude-code-scheduler/
├── .github/
│   └── workflows/
│       └── claude-scheduler.yml    # Main workflow configuration
├── README.md                       # This file
└── .gitignore                      # Git ignore rules
```

## 🔒 Security

- Your Anthropic API key is stored securely as a GitHub secret
- The workflow only has access to your repository's code
- No sensitive data is exposed in logs

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Anthropic](https://www.anthropic.com/) for providing Claude AI
- [GitHub Actions](https://github.com/features/actions) for the automation platform
- The open-source community for inspiration and support

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/yourusername/claude-code-scheduler/issues) page
2. Create a new issue with detailed information about your problem
3. Include relevant logs and configuration details

---

**Note**: This project is designed to assist with development tasks but should not replace human oversight. Always review and test changes made by AI before deploying to production. 