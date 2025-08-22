def display_binary(num):
    return bin(num)[2:].zfill(8)  # show as 8-bit binary

def bitwise_operations():
    print("=== Bitwise Operations Menu ===")
    print("1. AND (&)")
    print("2. OR (|)")
    print("3. XOR (^)")
    print("4. NOT (~)")
    print("5. Left Shift (<<)")
    print("6. Right Shift (>>)")
    print("0. Exit")

    while True:
        choice = input("\nSelect operation (0-6): ")

        if choice == "0":
            print("Exiting program...")
            break

        if choice in ["1", "2", "3", "4", "5", "6"]:
            if choice == "4":  # NOT only needs one number
                a = int(input("Enter number: "))
                result = ~a
                print(f"\nResult (~{a}) = {result}")
                print(f"Decimal: {result}, Binary: {display_binary(result & 0xFF)}")
            else:
                a = int(input("Enter first number: "))
                b = int(input("Enter second number: "))

                if choice == "1":
                    result = a & b
                    op = "&"
                elif choice == "2":
                    result = a | b
                    op = "|"
                elif choice == "3":
                    result = a ^ b
                    op = "^"
                elif choice == "5":
                    result = a << b
                    op = "<<"
                elif choice == "6":
                    result = a >> b
                    op = ">>"

                print(f"\nResult ({a} {op} {b}) = {result}")
                print(f"Decimal: {result}, Binary: {display_binary(result)}")
        else:
            print("Invalid choice! Please enter a number between 0 and 6.")

if __name__ == "__main__":
    bitwise_operations()
