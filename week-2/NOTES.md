# WEEK 2: ADVANCED LINUX & CTF - NOTES

## 🔑 Advanced Concepts

### 1. SSL/TLS Connections
```bash
openssl s_client -connect localhost:30001
# Encrypted connection to SSL service
```

### 2. Port Scanning
```bash
nmap -p 31000-32000 localhost
nmap -p 31000-32000 -sV localhost  # Version detection
```

### 3. SUID Binaries
```bash
ls -l binary
-rwsr-x--- (S = SUID bit)
# Executes as owner (usually root)
```

### 4. Cron Jobs
```bash
cat /etc/cron.d/cronjob_bandit22
# Scheduled task running as specific user
```

### 5. Git Version Control
```bash
git log                    # Show history
git log -p                 # Show changes
git show commit_hash       # Show commit
git branch -a              # List branches
git tag                    # List tags
```

### 6. Privilege Escalation

**SUID Path:**
1. Find SUID binary with `ls -l`
2. Identify functionality
3. Find weakness (overflow, injection)
4. Exploit to run commands as owner

**Cron Path:**
1. Find cron jobs in `/etc/cron.d/`
2. Identify target with elevated privileges
3. Find writable file or script
4. Modify to execute your commands
5. Wait for cron execution

**Git Path:**
1. Check commit history
2. Find sensitive data in diffs
3. Restore or extract password

## 🛠️ Key Commands

```bash
# Nmap scanning
nmap -A -p 31000-32000 localhost

# OpenSSL connection
openssl s_client -connect localhost:30001

# Git analysis
git log -p | grep -i password
git show commit_hash

# Find SUID binaries
find / -perm -4000 2>/dev/null

# View cron jobs
cat /etc/cron.d/*

# Brute force with netcat
for i in {0000..9999}; do
    echo "bandit24 $i" | nc localhost 30002
done | grep Right
```

## 🎓 Concepts

1. **Network services** - Understand ports and protocols
2. **Encryption** - SSL/TLS protects data
3. **Privilege escalation** - Methods and techniques
4. **Version control** - Git reveals history
5. **Automation** - Scripts can exploit patterns
6. **Shell escapes** - Breaking restrictions
7. **Problem solving** - Apply all Week 1 skills

## 📚 Further Reading

- OWASP Privilege Escalation
- GTFOBins (SUID exploitation)
- Git Internals Guide
- OpenSSL Manual

**Last Updated:** October 11, 2026
