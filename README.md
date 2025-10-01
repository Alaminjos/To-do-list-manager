# To-do-list-manager
def add_task(tasks):
    task = input("Enter a task to add").strip()
    # it remove spaces to prevent adding empty task
    if not task:
    # it checks for empty space and send warning if found instead of crashing 
        print("Can't add an empty task please add some")
        return
    tasks.append(task)
    # it stores valid task
    print(f' Added task: "{task}"')

def view_tasks(tasks):
    if not tasks:
    # it send message if the task is empty 
        print("No tasks added yet")
        return
    print("Enter your task")
    for idx, task in enumerate(tasks, start=1):
        print(f"{idx}.{task}")
        # it display task numbered from 1
        print()
def remove_task(tasks):
    if not tasks:
    # it check if there is nothing to remove and send warning instead of crashing 
        print("Nothing to remove")
        return
    view_tasks(tasks)
    choice = input("Enter task to remove").strip()
    # it enable user to select a task to remove
    if not choice:
        print("No input provided")
        return
    try:
                num = int(choice)
    except ValueError:
        print("That is not a number, enter a valid number")
        return
            
    if 1 <= num <= len(tasks):
        removed = tasks.pop(num - 1)
        print(f'Removed task: "{removed}" ')
    else:
        print(f"Task number out of range please chose a number between 1 and {len(tasks)}")

def main():
    tasks = []
    menu = (
                        "\n--- To Do List Manager --- \n"
                        "1. Add task\n"
                        "2. View tasks\n"
                        "3. Quit\n"
                    )
while True:
            print(menu)
            choice = input("Choose (1-4):").strip()
            if choice == "1":
                add_task(tasks)
            elif choice == "2":
                view_tasks(tasks)
            elif choice == "3":
                remove_task(tasks)
            elif choice == "4" or choice.lower() in ("q", "quit", "exit"):
                print("Goodbye")
                break
            else:
                print("Invalid choice.")
    if __name__ == "__main__":
        main()            
