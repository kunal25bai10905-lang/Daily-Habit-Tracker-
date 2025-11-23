def add_habit(habit_list):
    date = input("Enter date (YYYY-MM-DD): ")
    habit = input("Enter habit description: ")
    done = input("Did you complete the habit? (yes/no): ")
    if done not in ['yes', 'no']:
        print("Invalid input. Please enter 'yes' or 'no'.")
        return
    habit_entry = {'date': date, 'habit': habit,'completed': done == 'yes'}
    habit_list.append(habit_entry)
    print("Habit added successfully.")

def view_habits(habit_list):
    if not habit_list:
        print("No habits tracked .")
        return
    print("Daily Habit Tracker:")
    for i, entry in enumerate(habit_list, start=1):
        status = "Completed" if entry['completed'] else "Not Completed"
        print(f"{i}. Date: {entry['date']}, Habit: {entry['habit']}, Status: {status}")

def main():
    habits = []
    while True:
        print("Daily Habit Tracker Menu:")
        print("1. Add Habit")
        print("2. View Habits")
        print("3. Exit")
        choice = input("Enter your choice (1/2/3): ")
        if choice == '1':
            add_habit(habits)
        elif choice == '2':
            view_habits(habits)
        elif choice == '3':
            print("Exiting Goodbye!")
            break
        else:
            print("Invalid choice. Please enter 1, 2, or 3.")
    main()
