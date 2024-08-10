# CLI Password Management Script

This Bash script is a simple command-line interface (CLI) for managing passwords. It allows you to add, retrieve, list, delete, and auto-generate passwords securely using a hidden file in your home directory.

## Features

- **Add Password**: Store a password for a given label.
- **Retrieve Password**: Retrieve and copy the password to the clipboard.
- **List Labels**: Display all stored labels.
- **Delete Password**: Delete a password associated with a label.
- **Auto-generate Password**: Automatically generate a secure password and store it.

## Prerequisites

Ensure the following tools are installed:

- `openssl`: Used for generating secure passwords.
- `xclip`: Used for copying passwords to the clipboard.

You can install them on a Debian-based system using:

```bash
sudo apt-get install openssl xclip
```

## Usage

### 1. Add a Password

To add a new password or update an existing one:

```bash
./script.sh add <label:password>
```

- **Example**: `./script.sh add email:mysecurepassword`

### 2. Retrieve a Password

To retrieve a stored password and copy it to the clipboard:

```bash
./script.sh get <label>
```

- **Example**: `./script.sh get email`

### 3. List All Labels

To list all stored labels:

```bash
./script.sh list
```

### 4. Delete a Password

To delete a password associated with a label:

```bash
./script.sh delete <label>
```

- **Example**: `./script.sh delete email`

### 5. Auto-generate a Password

To auto-generate a secure password for a label and store it:

```bash
./script.sh auto <label>
```

- **Example**: `./script.sh auto github`

## Script Overview

The script uses a hidden file located at `~/pm/.password_store` to store passwords. Each password is associated with a label in the format `label:password`.

- **File path**: `~/pm/.password_store`
- **Add or Update Password**: Validates the format, checks if the label exists, and either updates or stores the password.
- **Retrieve Password**: Fetches the password for the given label and copies it to the clipboard using `xclip`.
- **Auto-generate Password**: Generates a secure password using `openssl` and stores it under the specified label.

## Example Workflow

1. **Add a password**: `./script.sh add email:mysecurepassword`
2. **Retrieve and copy password**: `./script.sh get email`
3. **Auto-generate and store password**: `./script.sh auto github`
4. **List all labels**: `./script.sh list`
5. **Delete a password**: `./script.sh delete email`

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Contributions

Feel free to submit issues, forks, or pull requests to improve this project!
