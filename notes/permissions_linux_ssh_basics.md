# 🔐 Linux File Permissions & SSH Key Basics
## 🎯 chmod Syntax```bashchmod [options] permissions file```
---
## 📦 Octal Mode – Values and Meaning
| Value | Symbolic | Meaning             ||-------|----------|---------------------|| 7     | rwx      | read, write, execute|| 6     | rw-      | read, write         || 5     | r-x      | read, execute       || 4     | r--      | read only           || 0     | ---      | no access           |
---
## 🧑‍💻 Three-Digit Structure
Each digit represents access for:
1. **Owner**2. **Group**3. **Others**
Example:```bashchmod 754 file#    ^ owner: rwx → full access#     ^ group: r-x → read and execute#      ^ others: r-- → read only```
---
## 📌 Common chmod Use Cases
| Command         | Permissions | Meaning                                 | Use Case                            ||-----------------|-------------|------------------------------------------|-------------------------------------|| `chmod +x`      | add exec    | Add executable permission                | For `.sh` scripts or binaries       || `chmod 600`     | rw-------   | Only owner can read/write                | SSH private key (`id_ed25519`)      || `chmod 700`     | rwx------   | Full access for owner only              | `.ssh/` directory or private files  || `chmod 644`     | rw-r--r--   | Owner read/write, others read only       | Config files or docs                || `chmod 755`     | rwxr-xr-x   | Owner full, others read & execute        | Shared scripts or programs          |
---
## ✅ chmod Examples```bashchmod 700 ~/.ssh/             # SSH key directorychmod 600 ~/.ssh/id_ed25519   # Private SSH keychmod +x backup.sh            # Make a script executablechmod 755 my_script.sh        # Script for sharing```
---
## 🔑 Why Use `id_ed25519` for SSH?
- `id_ed25519` is a key using the Ed25519 algorithm — **modern, secure, and fast**.- It’s the **recommended key type** over RSA for SSH.- Use `chmod 600` on the private key (`id_ed25519`) to restrict access.- The **public key** (`id_ed25519.pub`) is safe to share with servers or GitHub.
---
## 🚀 How to Add Your SSH Key to GitHub
1. Generate a key:```bash ssh-keygen -t ed25519 -C "your_email@example.com"```
2. Display public key content:```bash cat ~/.ssh/id_ed25519.pub```
3. In GitHub:     Go to **Settings → SSH and GPG keys → New SSH key**, paste the key.
4. Test the connection:```bash ssh -T git@github.com```If successful, you’ll see:```Hi username! You've successfully authenticated, but GitHub does not provide shell access.```
---
## 📋 Permissions Recap Table
| Command       | Permissions | Description                              ||---------------|-------------|------------------------------------------|| `chmod 600`   | rw-------   | Private key — owner-only read/write      || `chmod 644`   | rw-r--r--   | Public key — read by everyone            || `chmod 700`   | rwx------   | Private directory or script               |
---
## 💡 Tips
- Always use `chmod 600` for private keys.- Use `chmod +x` to make scripts runnable.- Use `chmod 700` for private folders.- Check permissions with:```bashls -l```
---
## 🔗 Useful Links
- [GitHub SSH Docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)- [Ed25519 - Wikipedia](https://en.wikipedia.org/wiki/EdDSA#Ed25519)"""
path = Path("/mnt/data/linux_file_permissions_ssh_guide.md")path.write_text(markdown_content)path
