def add_habit(habits):
    date = input("Enter date (YYYY-MM-DD): ")
    habit = input("Which habit did you do? ")
    done = input("Did you complete it? (yes/no): ").lower()

    if done == 'yes':
        status = True
    else:
        status = False

    habits.append({'date': date, 'habit': habit, 'completed': status})
    print("Your habit entry added!")

def view_habits(habits):
    if len(habits) == 0:
        print("No habits have been added yet.")
    else:
        print("\nLog your habits:")
        for i, entry in enumerate(habits, 1):
            state = "Done" if entry['completed'] else "Not finished"
            print(f"{i}. {entry['date']} - {entry['habit']} : {state}")

def main():
    habit_list = []
    while True:
        print("\nMenu:\n1. Add habit\n2. Show habits\n3. Exit")
        option = input("Choose (1/2/3): ")
        if option == '1':
            add_habit(habit_list)
        elif option == '2':
            view_habits(habit_list)
        elif option == '3':
            print("Goodbye! Keep track of these habits.")
            break
        else:
            print("Please enter a valid option.")
    main()

    
