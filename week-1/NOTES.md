# WEEK 1: LINUX & CYBERSECURITY FUNDAMENTALS - DETAILED NOTES

## 🔑 Core Concepts

### 1. Linux File System

### 2. File Permissions (rwx)

### 3. Essential Commands

**Navigation:**
- `pwd` - Print working directory
- `cd /path` - Change directory
- `ls -la` - List all files

**File Operations:**
- `cat file` - Display file contents
- `file filename` - Detect file type
- `grep pattern file` - Search text
- `find . -name pattern` - Find files

### 4. SSH (Secure Shell)
```bash
ssh user@host -p port
ssh -i private_key user@host
```

Key authentication is more secure than passwords.

### 5. Data Encoding

**Base64** (text encoding):
```bash
base64 -d encoded.txt
```

**ROT13** (character rotation):
```bash
tr 'a-zA-Z' 'n-za-mN-ZA-M'
```

**Hexdump** (hex ↔ binary):
```bash
xxd -r hex.txt > binary
```

## 🛠️ Tools Reference

| Command | Purpose |
|---------|---------|
| cat | Display file |
| grep | Search text |
| find | Search files |
| sort | Sort lines |
| uniq -u | Find unique lines |
| strings | Extract text from binary |
| base64 | Encode/decode |
| xxd | Hexdump |
| ssh | Remote access |
| nc | Netcat (TCP) |

## 🎓 Key Takeaways

1. Master Linux fundamentals - file system, permissions, commands
2. Command-line tools are more powerful than GUIs
3. Encoding ≠ Encryption (encoding is reversible)
4. Problem solving - break challenges into smaller steps
5. Documentation - record solutions for reference

**Last Updated:** October 11, 2026
