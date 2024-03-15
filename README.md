class Task:
    def __init__(self, name, priority, due_date):
        self.name = name
        self.priority = priority
        self.due_date = due_date
        self.completed = False

def add_task(tasks):
    # Get task details from user input
    name = input("Enter task name: ")
    priority = input("Enter task priority (high/medium/low): ")
    due_date = input("Enter due date (YYYY-MM-DD): ")

    # Create a new task
    task = Task(name, priority, due_date)
    tasks.append(task)
    print("Task added successfully!")

def display_tasks(tasks):
    for task in tasks:
        print(f"{task.name} ({task.priority}) - Due: {task.due_date} {'(Completed)' if task.completed else ''}")

def main():
    tasks = []  # List to store tasks

    # Load tasks from file (if any)

    while True:
        print("\nMenu:")
        print("1. Add Task")
        print("2. View Tasks")
        print("3. Exit")
        choice = input("Enter your choice: ")

        if choice == "1":
            add_task(tasks)
        elif choice == "2":
            display_tasks(tasks)
        elif choice == "3":
            # Save tasks to file
            break
        else:
            print("Invalid choice. Try again.")

if __name__ == "__main__":
    main()
