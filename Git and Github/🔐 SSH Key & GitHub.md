```bash
# Generate an SSH key (press Enter to accept defaults)
ssh-keygen -t ed25519 -C "you@example.com"

# Add the key to the ssh-agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Copy the public key
cat ~/.ssh/id_ed25519.pub
```

Paste the output into **GitHub → Settings → SSH and GPG keys**.

> **Tip:** `gh auth login --with-token <token>` will add the key automatically if the token has `write:public_key`.

