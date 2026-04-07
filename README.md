# FinSafe — Transaction Validator

A console-based Java application that simulates a digital wallet. It validates every spend request against the user's balance and maintains a transaction log for auditing.

---

## What It Does

- Creates a user account with a name and starting balance
- Allows deposits, withdrawals, and balance checks
- Blocks overdraft attempts with a custom exception
- Keeps a log of the last 5 successful transactions
- Handles all invalid inputs with clear error messages

---

## Project Structure

```
FinSafe/
├── Account.java          # Account class with balance logic and transaction history
├── FundsException.java   # Custom exception for insufficient funds
└── Main.java             # Entry point with menu and user interaction
```

---

## How to Compile and Run

Make sure Java (JDK 8 or above) is installed.

```bash
# Compile all files
javac Account.java FundsException.java Main.java

# Run the application
java Main
```

---

## Menu Options

| Option | Action |
|--------|--------|
| 1      | Deposit funds into the account |
| 2      | Withdraw / Spend from the account |
| 3      | View Mini Statement (last 5 transactions) |
| 4      | Exit the application |

---

## Sample Session

```
Enter Account Holder Name : Arjun
Enter Initial Balance      : ₹5000

Account created for Arjun

========= FinSafe Menu =========
1. Deposit
2. Withdraw / Spend
3. View Mini Statement
4. Exit
================================
Enter your choice: 2
Enter spend amount: ₹6000
Error: Insufficient funds! Available balance: ₹5000.0

Enter your choice: 1
Enter deposit amount: ₹2000
Successfully deposited ₹2000.0

Enter your choice: 3

========= Mini Statement =========
Account Holder : Arjun
Current Balance: ₹7000.0
Last 1 Transactions:
  1. Deposited: ₹2000.0
==================================
```

---

## Error Handling

| Scenario | Error Raised |
|----------|--------------|
| Spend amount exceeds balance | `FundsException` (custom) |
| Negative or zero amount entered | `IllegalArgumentException` |
| Invalid menu option | Default case message |

---

## Requirements

- Java JDK 8 or higher
- No external libraries needed
