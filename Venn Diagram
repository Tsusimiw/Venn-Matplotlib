from matplotlib_venn import venn3
import matplotlib.pyplot as plt

# Initialize sets with the universal set (containing all elements)
A = set()
B = set()
C = set()

# Function to check if a string is numeric
def is_numeric(input_str):
    try:
        float(input_str)
        return True
    except ValueError:
        return False

# Create an interactive loop to display the menu and handle user inputs
while True:
    print("Menu:")
    print("1. 1st Set:", A)
    print("2. 2nd Set:", B)
    print("3. 3rd Set:", C)
    print("4. Generate Venn-Diagram")
    print("5. Exit")

    choice = input("Select an option: ")

    # Menu
    if choice == '1':
        while True:
            new_element = input("Enter a numeric element for the 1st set: ")
            if is_numeric(new_element):
                A.add(float(new_element))
                break
            else:
                print("Invalid input. Enter a numeric number.")
    elif choice == '2':
        while True:
            new_element = input("Enter a numeric element for the 2nd set: ")
            if is_numeric(new_element):
                B.add(float(new_element))
                break
            else:
                print("Invalid input. Enter a numeric number.")
    elif choice == '3':
        while True:
            new_element = input("Enter a numeric element for the 3rd set: ")
            if is_numeric(new_element):
                C.add(float(new_element))
                break
            else:
                print("Invalid input. Enter a numeric number.")
    elif choice == '4':
        if A or B or C:
            venn = venn3(subsets=[A, B, C], set_labels=('A', 'B', 'C'))

            # Ensure that labels are available before iterating
            if venn.set_labels:
                # Set the text for the regions
                label_100 = venn.get_label_by_id('100')
                if label_100:
                    label_100.set_text('\n'.join(map(str, A - B - C)))

                label_010 = venn.get_label_by_id('010')
                if label_010:
                    label_010.set_text('\n'.join(map(str, B - A - C)))

                label_001 = venn.get_label_by_id('001')
                if label_001:
                    label_001.set_text('\n'.join(map(str, C - A - B)))

                label_110 = venn.get_label_by_id('110')
                if label_110:
                    label_110.set_text('\n'.join(map(str, A & B - C)))

                label_101 = venn.get_label_by_id('101')
                if label_101:
                    label_101.set_text('\n'.join(map(str, A & C - B)))

                label_011 = venn.get_label_by_id('011')
                if label_011:
                    label_011.set_text('\n'.join(map(str, B & C - A)))

                label_111 = venn.get_label_by_id('111')
                if label_111:
                    label_111.set_text('\n'.join(map(str, A & B & C)))

                plt.title("Venn Diagram")
                plt.show()  # Display the Venn diagram
            else:
                print("Venn diagram labels are not available.")
        else:
            print("Please enter elements for at least one set before generating the diagram.")
    elif choice == '5':
        break
    else:
        print("Invalid input. Try again.")
