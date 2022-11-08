### Atm ###
This is the program about the ATM machine
### User Program ###
class user:
    global name
    name=input("Name on your bank account? ")
    global balance
    balance=float(input("Your current balance? "))
    global printMenu
    def printMenu():
        print(name,"Welcome to the Diari Bank")
        print("Enter 'b'(balance), 'd'(deposit), 'w'(withdraw), or'q'(quit)")
    global getTransaction
    def getTransaction():
        transaction=str(input("What would you like to do? "))
        return transaction
    global withdraw
    def withdraw(bal,amt):
        balance=bal-amt
        if balance<0:
            balance=balance-10
    global formatCurrency
    def formatCurrency(amt):
        return "$%.2f" %amt

### MAIN PROGRAM ###
class mainProgram:
    printMenu()
    command=str(getTransaction())

    while command!="q":
        if (command=="b"):
            print(name,"Your current balance is",formatCurrency(balance))
            printMenu()
            command=str(getTransaction())
        elif (command=="d"):
            amount=float(input("Amount to deposit? "))
            balance=balance+amount
            printMenu()
            command=str(getTransaction())
        elif (command=="w"):
            amount=float(input("Amount to withdraw? "))
            withdraw(balance,amount)
            printMenu()
            command=str(getTransaction())
        else:
            print("Incorrect command. Please try again.")
            printMenu()
            command=str(getTransaction())

print(name,"Goodbye! See you again soon")
