# Week 4 Assignment: Expense Categorizer

# Get user input
amount = input("Enter the expense amount: ")
description = input("Enter the expense description: ").strip()

# Validate description
if description == "":
    print("Error: Description cannot be empty.")

# Validate amount
elif not amount.isdigit():
    print("Error: Amount must be a whole number.")

elif int(amount) <= 0:
    print("Error: Amount must be greater than 0.")

else:
    amount = int(amount)
    desc = description.lower()

    # Categorize the expense
    if "bus" in desc or "taxi" in desc or "fuel" in desc:
        category = "Transport"

    elif "lunch" in desc or "market" in desc or "groceries" in desc:
        category = "Food"

    elif "rent" in desc or "electricity" in desc or "water" in desc:
        category = "Utilities"

    else:
        category = "Other"

    # Display results
    print("\nExpense Summary")
    print("---------------------------")
    print(f"Amount: {amount}")
    print(f"Description: {description}")
    print(f"Category: {category}")

    # Flag large expenses
    if amount > 5000:
        print("Status: REVIEW REQUIRED - Expense exceeds 5000.")
    else:
        print("Status: Approved")
