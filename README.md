# codesaoftt_tasking
# Simple To-Do List Application (Command-Line Version)

# Initialize an empty list to store tasks
tasks = []

# Function to display the tasks
def display_tasks():
    print("\nYour To-Do List:")
    if not tasks:
        print("No tasks added yet!")
    else:
        for idx, task in enumerate(tasks, start=1):
            print(f"{idx}. {task}")
    print("-" * 30)

# Function to add a task
def add_task():
    task = input("Enter the task you want to add: ")
    tasks.append(task)
    print(f"Task '{task}' added successfully!")

# Function to remove a task
def remove_task():
    display_tasks()
    try:
        task_num = int(input("Enter the task number to remove: "))
        if 1 <= task_num <= len(tasks):
            removed = tasks.pop(task_num - 1)
            print(f"Task '{removed}' removed successfully!")
        else:
            print("Invalid task number. Please try again.")
    except ValueError:
        print("Invalid input. Please enter a valid number.")

# Main menu to interact with the user
def to_do_list_app():
    while True:
        print("\nTo-Do List Application")
        print("1. View To-Do List")
        print("2. Add Task")
        print("3. Remove Task")
        print("4. Exit")
        
        choice = input("Enter your choice (1-4): ")
        
        if choice == '1':
            display_tasks()
        elif choice == '2':
            add_task()
        elif choice == '3':
            remove_task()
        elif choice == '4':
            print("Exiting To-Do List Application. Goodbye!")
            break
        else:
            print("Invalid choice. Please choose between 1 and 4.")
 ##run the application       
to_do_list_app()
