# Git & GitHub Complete Commands Cheat Sheet

**Purpose:** Git aur GitHub ki important commands, unka work aur practical examples.

## Git & GitHub Introduction

### Git kya hai?

Git ek Version Control System (VCS) hai jo project ki files mein hone wali changes ko track karta hai.

### GitHub kya hai?

GitHub ek online platform hai jahan hum apni Git repositories upload aur host karte hain aur doosre developers ke saath collaborate karte hain.

## Git vs GitHub

### Git

- Version Control Tool
- Locally work karta hai.
- Changes track karta hai.
- Internet ke baghair bhi work karta hai.

### GitHub

- Cloud-based Platform
- Online work karta hai.
- Repositories host karta hai.
- Online collaboration provide karta hai.

## Git Configuration

**Note:** Ye commands Git ko pehli baar setup karte waqt run karni hoti hain.

### 1. Username set karna

```bash
git config --global user.name "Your Name"
```

**Work:** Git mein apna username set karta hai.

### 2. Email set karna

```bash
git config --global user.email "your-email@example.com"
```

**Work:** Git mein apna email address set karta hai.

### 3. Configuration check karna

```bash
git config --global --list
```

**Work:** Git ki configured settings show karta hai.

**Note:** `--global` ka matlab hai ke ye settings tumhare computer ke sabhi Git projects ke liye apply hongi.

## Git Branch

Branch code ki ek separate working line hoti hai.

### 1. Branch check karna

```bash
git branch
```

**Work:** Local branches show karta hai.

### 2. New branch create karna

```bash
git branch feature
```

**Work:** `feature` naam ki new branch create karta hai.

### 3. Branch change karna

```bash
git switch feature
```

**Work:** `feature` branch par switch karta hai.

### 4. Branch create aur switch ek saath

```bash
git switch -c feature
```

**Work:** New branch create karke us par switch karta hai.

### 5. Branch rename karna

git branch -M main

**Work:** -M forcefully branch rename karta hai. Agar same naam ki branch pehle se maujood ho, to -M usay overwrite kar sakta hai.

=======
# Repository kya hoti hai?

Repository (Repo) ek project folder hota hai jismein project ki files aur unki version history hoti hai.

**Example:**

```text
my-project/
├── .git/
├── index.html
├── style.css
├── script.js
└── README.md
```

`.git` ek hidden folder hai jisme Git repository ka internal data aur history store hoti hai.

---

# 1. Repository Create Karna

Repository create karne ke 2 methods hain.

### Method 1: GitHub Website

1. GitHub open karo.
2. New Repository par click karo.
3. Repository name enter karo.
4. Public ya Private select karo.
5. Create Repository par click karo.

Website: [GitHub](https://github.com/)

### Method 2: Terminal se Local Repository

# 1. Apne project folder mein terminal open karo.

```bash
git init
```

**Work:** Current folder mein Git repository initialize karta hai.

Background mein `.git` hidden folder create hota hai.

**Example:**

```text
my-project/
├── .git/
├── index.html
└── style.css
```

**Important:** `git init` normally ek project mein sirf pehli baar run karte hain.

---

# 2. Changes Staging Area

### 1. All changes add karna

```bash
git add .
```

**Work:** Current directory aur uski subdirectories ki new aur modified files aur deletions ko staging area mein add karta hai.

### 2. Specific file add karna

```bash
git add index.html
```

**Work:** Sirf `index.html` ko staging area mein add karta hai.

### 3. All changes stage karna

```bash
git add -A
```

**Work:** Repository ki new, modified aur deleted files sabko staging area mein add karta hai.

---

# 3. Git Commit

```bash
git commit -m "first commit"
```

**Work:** Staging area ki changes ka snapshot local repository mein save karta hai.

### Command Breakdown

| Part | Meaning |
|---|---|
| `git` | Git tool |
| `commit` | Changes ka snapshot save karna |
| `-m` | Commit message provide karna |
| `"first commit"` | Commit ka message |

**Example:**

```bash
git commit -m "Added homepage"
```

---

# 4. Git Remote

Remote repository ka matlab hai online Git repository, jaise GitHub repository.

### 1. GitHub repository connect karna

```bash
git remote add origin YOUR_REPOSITORY_URL
```

**Example:**

```bash
git remote add origin https://github.com/username/my-project.git
```

**Work:** Local repository ko GitHub repository ke saath connect karta hai.

### Command Breakdown

| Part | Meaning |
|---|---|
| `remote` | Remote repository manage karna |
| `add` | New remote add karna |
| `origin` | Remote ka nickname |
| `URL` | GitHub repository ka address |

### 2. Remote check karna

```bash
git remote -v
```

**Work:** Connected remote repositories ke URLs show karta hai.

### 3. Remote remove karna

```bash
git remote remove origin
```

**Work:** Local repository se `origin` remote connection remove karta hai. GitHub repository delete nahi hoti.

---

# 5. Git Branch Rename

```bash
git branch -M main
```

**Work:** Current branch ka naam `main` rakhta hai.

**Note:** `-M` forcefully branch rename karta hai. Agar same naam ki branch pehle se maujood ho, to `-M` usay overwrite kar sakta hai.

**Work:** Current branch ka naam `main` kar deta hai. Agar pehle branch ka naam `master` ho, to usay `main` mein rename kar deta hai.

### Command Breakdown

| Part | Meaning |
|---|---|
| `branch` | Branches se related command |
| `-M` | Current branch ko forcefully rename karna |
| `main` | Naya branch name |

**Important:**

- Ye new branch create nahi karta, balki current branch ka naam change karta hai.
- `-M` existing same-name branch ke conflict ko forcefully handle karta hai.
- Rename check karne ke liye:

```bash
git branch
```

---

# 6. Git Push

```bash
git push -u origin main
```

**Work:** Local commits ko GitHub ki `main` branch par upload karta hai.

### Command Breakdown

| Part | Meaning |
|---|---|
| `push` | Commits upload karna |
| `-u` | Upstream tracking set karna |
| `origin` | Remote repository |
| `main` | Branch name |

**Important:** First successful push ke baad aksar sirf ye command use kar sakte ho:

```bash
git push
```
# 11. Git Pull

```bash
git pull
```

**Work:** Remote repository se latest changes download karke current branch mein integrate karta hai.

### Specific Remote aur Branch

```bash
git pull origin main
```

**Example:** Kisi teammate ne GitHub par changes upload ki hain. Tum `git pull` se apni local branch update kar sakte ho.

---

# 12. Git Clone

```bash
git clone REPOSITORY_URL
```

**Work:** GitHub ki existing repository ki copy apne computer par download karta hai.

**Example:**

```bash
git clone https://github.com/username/my-project.git
```

Clone karne ke baad repository ka folder tumhare computer par create ho jata hai.

---

# 13. Git Fetch

```bash
git fetch
```

**Work:** Remote repository se latest updates download karta hai, lekin automatically current branch mein merge nahi karta.

### Difference

- `git fetch` = Remote updates download karta hai.
- `git pull` = Updates download karke integrate bhi karta hai.

---

# 18. Git Merge

```bash
git merge feature
```

**Work:** `feature` branch ki changes current branch mein merge karta hai.

**Example:**

```bash
git switch main
git merge feature
```

Is example mein `feature` branch ki changes `main` branch mein merge hongi.

---

# 21. .gitignore

`.gitignore` ek special file hai jismein hum un files aur folders ke names likhte hain jinhein Git track nahi karega.

### Example `.gitignore`

```text
node_modules/
.env
.next/
dist/
```

### Work

- `node_modules/` ko ignore karta hai.
- `.env` ko ignore karta hai.
- `.next/` ko ignore karta hai.
- `dist/` ko ignore karta hai.

**Important:** Jo files pehle se Git track kar raha hai, unhein `.gitignore` automatically untrack nahi karta.