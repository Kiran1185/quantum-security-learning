# WEEK 1: BANDIT SOLUTIONS (Levels 0-15)

## 🔓 Level 0 → 1

**Challenge:** Read password from README file

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
# Password: bandit0

$ cat README
boJ9jbbUNNfktd0TPqR3cqKBmqKBvJT
```

**Password for Level 1:** boJ9jbbUNNfktd0TPqR3cqKBmqKBvJT

---

## 🔓 Level 1 → 2

**Challenge:** Read file named "-" (dash)

```bash
$ cat ./-
CV1DtqXF6fjGNoG6B1GPP7OK2Myp5QPe
```

**Lesson:** Use `./` prefix to escape special characters

**Password for Level 2:** CV1DtqXF6fjGNoG6B1GPP7OK2Myp5QPe

---

## 🔓 Level 2 → 3

**Challenge:** File with spaces in name

```bash
$ cat "spaces in this filename"
UmHadQclWmgdLKFudyKo5ZNg6qdTL4Aj
```

**Lesson:** Quote filenames with spaces

**Password for Level 3:** UmHadQclWmgdLKFudyKo5ZNg6qdTL4Aj

---

## 🔓 Level 3 → 4

**Challenge:** Find hidden file in "inhere" directory

```bash
$ cd inhere
$ ls -a
.  ..  .hidden

$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

**Lesson:** Hidden files start with `.` and need `ls -a`

**Password for Level 4:** pIwrPrtPN36QITSp3EQaw936yaFoFgAB

---

## 🔓 Level 4 → 5

**Challenge:** Find readable file among 10 binary files

```bash
$ cd inhere
$ file *
-file00: data
-file01: data
...
-file07: ASCII text

$ cat -file07
koReBOKuIDDepwhWwgnYOrisJ7QvxJqJ
```

**Lesson:** Use `file` command to detect file types

**Password for Level 5:** koReBOKuIDDepwhWwgnYOrisJ7QvxJqJ

---

## 🔓 Level 5 → 6

**Challenge:** Find human-readable file, 1033 bytes

```bash
$ find . -size 1033c
./maybehere07/./file2

$ cat ./maybehere07/./file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

**Lesson:** Use `find -size` to filter by file size

**Password for Level 6:** DXjZPULLxYr17uwoI01bNLQbtFemEgo7

---

## 🔓 Level 6 → 7

**Challenge:** File owned by bandit7, group bandit6, 33 bytes

```bash
$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password

$ cat /var/lib/dpkg/info/bandit7.password
HwR3gluBohxV7PVk5x4rPs0i3hnOMTkx
```

**Lesson:** Use find with multiple filters

**Password for Level 7:** HwR3gluBohxV7PVk5x4rPs0i3hnOMTkx

---

## 🔓 Level 7 → 8

**Challenge:** Password next to word "millionth"

```bash
$ grep millionth data.txt
millionth   cvX2JJa4CFAjoYMYw3CqK51bQEoJ7mzh
```

**Lesson:** grep for pattern matching

**Password for Level 8:** cvX2JJa4CFAjoYMYw3CqK51bQEoJ7mzh

---

## 🔓 Level 8 → 9

**Challenge:** Password appears once, others appear multiple times

```bash
$ sort data.txt | uniq -u
UsvVyFSfZccR1xTgR4b4b6i5d2CarJUm
```

**Lesson:** sort + uniq -u finds unique lines

**Password for Level 9:** UsvVyFSfZccR1xTgR4b4b6i5d2CarJUm

---

## 🔓 Level 9 → 10

**Challenge:** Password after "==" in binary file

```bash
$ strings data.txt | grep ==
========== the*2i"4
========== password is truKLAacFktMINGY2QnWWaXbNYto6xAHP
```

**Lesson:** strings extracts readable text from binary

**Password for Level 10:** truKLAacFktMINGY2QnWWaXbNYto6xAHP

---

## 🔓 Level 10 → 11

**Challenge:** Data is base64 encoded

```bash
$ cat data.txt | base64 -d
The password is IFukwdDL6lVrkgQ2RyNGyRyKXnPv5XWu
```

**Lesson:** base64 -d decodes

**Password for Level 11:** IFukwdDL6lVrkgQ2RyNGyRyKXnPv5XWu

---

## 🔓 Level 11 → 12

**Challenge:** Data is ROT13 encoded

```bash
$ cat data.txt | tr 'a-zA-Z' 'n-za-mN-ZA-M'
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6mAcMs
```

**Lesson:** tr rotates characters

**Password for Level 12:** 5Te8Y4drgCRfCx8ugdwuEX8KFC6mAcMs

---

## 🔓 Level 12 → 13

**Challenge:** Hexdumped file with multiple compression layers

```bash
$ xxd -r data.txt > data.bin
$ file data.bin
gzip compressed data

$ gunzip data.bin
$ file data
bzip2 compressed data

# Continue decompressing...
```

**Lesson:** Handle multiple compression layers

**Password for Level 13:** 8ZjyCRiBWFHxkT0s8hqq1wK3VV7XCSTX

---

## 🔓 Level 13 → 14

**Challenge:** Use private SSH key to login as bandit14

```bash
$ chmod 600 sshkey.private
$ ssh -i sshkey.private bandit14@localhost
$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlM4its2Eq8xTmJ0qc
```

**Lesson:** SSH key authentication

**Password for Level 14:** 4wcYUJFw0k0XLShlM4its2Eq8xTmJ0qc

---

## 🔓 Level 14 → 15

**Challenge:** Send password to localhost:30000

```bash
$ nc localhost 30000
4wcYUJFw0k0XLShlM4its2Eq8xTmJ0qc
Correct!
BfMYafe2bqDsFveSyimRVIVyE21E2vU
```

**Lesson:** Netcat for TCP connections

**Password for Level 15:** BfMYafe2bqDsFveSyimRVIVyE21E2vU

---

## 📊 Summary

| Level | Tool | Concept |
|-------|------|---------|
| 0-5 | cat, file, find | Basic commands |
| 6-10 | grep, sort, strings | Text processing |
| 11-15 | base64, tr, xxd, ssh, nc | Encoding & networking |

**Complete! Ready for Week 2** ✅
