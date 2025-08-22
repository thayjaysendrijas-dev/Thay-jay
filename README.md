# Thay-jay







def display_binary(value):
    # Displays the value in decimal and 8-bit binary format
    return f"{value} (bin: {value:08b})"

def bitwise_and(a, b):
    return a & b

def bitwise_or(a, b):
    return a | b

def bitwise_xor(a, b):
    return a ^ b

def bitwise_not(a):
    return ~a

def left_shift(a, n):
    return a << n

def right_shift(a, n):
    return a >> n

def menu():
    print("\nBitwise Operation Menu:")
    print("1. AND (&)")
    print("2. OR (|)")
    print("3. XOR (^)")
    print("4. NOT (~)")
    print("5. Left Shift (<<)")
    print("6. Right Shift (>>)")
    print("0. Exit")

def main():
    while True:
        menu()
        choice = input("Select an operation (0-6): ")
        if choice == "0":
            print("Exiting...")
            break

        if choice in ["1", "2", "3"]:
            a = int(input("Enter first integer (a): "))
            b = int(input("Enter second integer (b): "))
            if choice == "1":
                result = bitwise_and(a, b)
                op = "&"
            elif choice == "2":
                result = bitwise_or(a, b)
                op = "|"
            else:
                result = bitwise_xor(a, b)
                op = "^"
            print(f"\n{a} {op} {b} = {display_binary(result)}")
        elif choice == "4":
            a = int(input("Enter integer (a): "))
            result = bitwise_not(a)
            # For display, mask to 32 bits for clarity (Python's ~ is infinite bits)
            print(f"\n~{a} = {display_binary(result & 0xFFFFFFFF)}")
        elif choice == "5":
            a = int(input("Enter integer (a): "))
            n = int(input("Enter shift amount: "))
            result = left_shift(a, n)
            print(f"\n{a} << {n} = {display_binary(result)}")
        elif choice == "6":
            a = int(input("Enter integer (a): "))
            n = int(input("Enter shift amount: "))
            result = right_shift(a, n)
            print(f"\n{a} >> {n} = {display_binary(result)}")
        else:
            print("Invalid choice, try again.")

if __name__ == "__main__":
    main()






