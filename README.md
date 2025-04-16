# Assignment3Test

def staff_info():
    count = 10000  
    print("Printing Requisitions:")

    while True:
        date = input("Date (dd/mm/yyyy): ")
        staff_id = input("Staff ID: ")
        staff_name = input("Staff Name: ")
        count += 1  
        print("Requisition ID:", count)
        
        again = input("Do you want to enter another? (yes/no): ")
        if again.lower() != "yes":
            break

staff_info()
def requisition_total():
    total_price = 0
    while True:
        product = input("Enter product name (or type 'done' to finish): ")
        if product.lower() == "done":
            break
        try:
            price = int(input(f"Enter price for {product}: $"))
        except ValueError:
            price = 0  
        total_price += price
    return total_price

def total():
    total_value = requisition_total()
    print("Requisition total = $" + str(total_value))
total()

def check_approval_status():
    total_requisitions = int(input("Enter the number of requisitions you want to submit : "))
    
    approved_count = 0
    pending_count = 0
    not_approved_count = 0

    for i in range(total_requisitions):
        print(f"\nProcessing requisition {i + 1}:")
        total = int(input("Enter the total amount of the products = "))
        
        if total <= 500:
            print("Status = Approved")
            staff_id = input("Enter the staff ID = ")
            requisition_id = input("Enter the requisition ID = ")
            approval_reference_number = staff_id + requisition_id[-3:]
            print("Your approval reference number is = " + approval_reference_number)
            approved_count += 1
        elif total <= 1000:
            print("Status = Pending")
            print("Approval reference number is not available")
            pending_count += 1
        else:
            print("Status = Not Approved")
            print("Approval reference number is not available")
            not_approved_count += 1

    print("\nStatistics:")
    print("Displaying the Requisition Statistics")
    print("The total number of requisitions submitted:", total_requisitions)
    print("The total number of approved requisitions:", approved_count)
    print("The total number of pending requisitions:", pending_count)
    print("The total number of not approved requisitions:", not_approved_count)

check_approval_status()
