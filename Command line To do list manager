def add_task(tasks):
    task = input("Enter a task to add: ").strip()
    if not task:
        print("Can't add an empty task. Please add something.")
        return
    tasks.append(task)
    print(f'Added task: "{task}"')

def view_tasks(tasks):
    if not tasks:
        print("No tasks added yet.")
        return
    print("Your tasks:")
    for idx, task in enumerate(tasks, start=1):
        print(f"{idx}. {task}")
    print()

def remove_task(tasks):
    if not tasks:
        print("Nothing to remove.")
        return
    view_tasks(tasks)
    choice = input("Enter the task number to remove: ").strip()
    if not choice:
        print("No input provided.")
        return
    try:
        num = int(choice)
    except ValueError:
        print("That is not a number. Enter a valid number.")
        return
    if 1 <= num <= len(tasks):
        removed = tasks.pop(num - 1)
        print(f'Removed task: "{removed}"')
    else:
        print(f"Task number out of range. Please choose a number between 1 and {len(tasks)}.")

def main():
    tasks = []
    menu = (
        "\n--- To Do List Manager ---\n"
        "1. Add task\n"
        "2. View tasks\n"
        "3. Remove task\n"
        "4. Quit\n"
    )
    while True:
        print(menu)
        choice = input("Choose (1-4): ").strip()
        if choice == "1":
            add_task(tasks)
        elif choice == "2":
            view_tasks(tasks)
        elif choice == "3":
            remove_task(tasks)
        elif choice == "4" or choice.lower() in ("q", "quit", "exit"):
            print("Goodbye!")
            break
        else:
            print("Invalid choice.")

if __name__ == "__main__":
    main()
