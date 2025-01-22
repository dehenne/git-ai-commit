# git-ai-commit

![GitHub release (latest by date)](https://img.shields.io/github/v/release/your-repo/git-ai-commit)
![GitHub](https://img.shields.io/github/license/your-repo/git-ai-commit)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/your-repo/git-ai-commit/ci.yml)

`git-ai-commit` integrates AI-powered commit message generation into your Git workflow. 
It leverages OpenAI's GPT-4 model to create concise and meaningful commit messages based on your staged or unstaged changes.

## Features
- **AI-Generated Commit Messages**: Automatically generate meaningful commit messages with a professional format.
- **Customizable Commit Templates**: Uses prefixes like `fix:`, `refactor:`, `docs:`, and ensures proper structure for both the headline and body.
- **Seamless Git Integration**: Supports standard Git commit parameters like `-a`, `-m`, and file-specific commits.
- **Editor Integration**: Opens the Git editor with a pre-filled commit message for manual review and edits.

## Prerequisites
- **Git**: Ensure Git is installed and configured on your system.
- **jq**: Used for JSON processing.
- **curl**: Required for API requests.
- **OpenAI API Key**: Access to OpenAI's GPT-4 API.

## Installation

1. Clone the repository or copy the script.
2. Save the script as `git-ai-commit` in a directory included in your `$PATH`, such as `/usr/local/bin/`.
3. Make the script executable:
   ```bash
   chmod +x /usr/local/bin/git-ai-commit
   ```
4. Ensure the required tools are installed:
   ```bash
   sudo apt update
   sudo apt install git jq curl
   ```

## Setup

1. Set your OpenAI API key:
   ```bash
   git-ai-commit --set-chatgpt-key YOUR_API_KEY
   ```
   This stores the API key in a `.env` file within the home directory of the current user.

2. Verify the setup by running:
   ```bash
   git-ai-commit --set-chatgpt-key <key>
   ```

## Usage

### Basic Usage

`git-ai-commit` supports standard Git commit options. Examples:

1. Stage all changes and generate a commit message:
   ```bash
   git-ai-commit -a
   ```

2. Commit specific files with a generated commit message:
   ```bash
   git-ai-commit file1.txt file2.txt
   ```

3. Commit with a custom message:
   ```bash
   git-ai-commit -m "fix: updated README"
   ```

4. Generate a commit message but review and edit it in the editor:
   ```bash
   git-ai-commit -a
   ```
   The script will:
   - Analyze your changes.
   - Generate a commit message with a formatted headline and body.
   - Open your editor with the pre-filled commit message.

### Example Commit Message Format

```
fix: correct typo in README

This fixes a small typo in the installation section of the README file. It ensures that the instructions are clear and accurate for users setting up the tool.
```

## Debugging

If you encounter errors:
- Ensure the API key is correctly set and valid.
- Verify that your changes are staged or unstaged but present.
- Check for missing dependencies like `jq` or `curl`.

## Uninstallation

To remove `git-ai-commit`, simply delete the script:
```bash
sudo rm /usr/local/bin/git-ai-commit
```
Also, remove the `.env` file if it exists:
```bash
rm $HOME/.git-ai-commit.env
```

## Contributing
Feel free to submit issues or contribute to this project by opening a pull request.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

