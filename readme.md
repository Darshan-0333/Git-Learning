🔁 Git Workflow: Rebase and Merge

🎯 Goal

- Create two branches: master and payment

- Do commits on both branches

- Rebase payment branch on top of master

- Merge payment into master with clean history

✅ Step-by-Step Process

📌 Step 1: Initialize Git & First Commit in master

git init
git add .
git commit -m "first commit - button added"

📌 Step 2: Second Commit in master

git add .
git commit -m "second commit - login added"

📌 Step 3: Create payment Branch & Add Commits

git checkout -b payment
git add .
git commit -m "payment - first commit - payment added"
git add .
git commit -m "payment - second commit - upi added"

📌 Step 4: Add Another Commit in master

git checkout master
git add .
git commit -m "footer - third commit - footer added"

🔁 Step 5: Rebase payment on Top of master

git checkout payment
git rebase master

⚠️ If conflict occurs (e.g., in first.js):

# Solve conflict manually
git add .
git rebase --continue

🔀 Step 6: Merge payment into master

git checkout master
git merge payment

✅ Fast-forward merge – no extra merge commit

✅ Final State

Both branches contain all features: button, login, footer, payment, and upi

History is clean and linear

No unnecessary merge commits

📊 Git Graph Visual

master:
A -- B -- C  (button, login, footer)
             \
payment:      D -- E (payment, upi) => rebased on C => linear history

💡 Why Rebase Before Merge?

Keeps history clean

Avoids merge clutter

Makes future debugging and reviewing easier
