
tasks = [] 
 
while True: 
    print("\n1. Add task")
    print("2. Show tasks")
    print("3. Complete task")
    print("4. Delete task")
    print("5. Exit")
    choice = input("Select an option (1-5): ")
    
    if choice == '1':  
        task = input("Enter task: ")
        tasks.append({"task": task, "completed": False})  
        print("Task added.")
        
    elif choice == '2':  
        if not tasks:  
            print("No tasks.")
        else:
            print("\nTasks:")
            for i in range(len(tasks)):
                task = tasks[i]
                
                if task["completed"]:
                    status = "Completed_Task"
                else:
                    status = "Pending_Task"
            
                print(i + 1, ". ", task[ 'task'], " [", status, "]", sep="")
                
    elif choice == '3':  
        task_num = input("Task number to complete: ")
        if task_num.isdigit():
            task_num = int(task_num)
            
            if 0 < task_num <= len(tasks):  
                task = tasks[task_num - 1]  
                task["completed"] = True 
                print("Task marked complete.")
            else:
                print("Invalid number.")
        else:
            print("Please enter a valid number.")
            
    elif choice == '4':  
        task_num = input("Task number to delete: ")
        if task_num.isdigit():
            task_num = int(task_num)
            
            if 0 < task_num <= len(tasks):  
                del tasks[task_num - 1]  
                print("Task deleted.")
            else:
                print("Invalid number.")
        else:
            print("Please enter a valid number.")
            
    elif choice == '5': 
        print("Goodbye!")
        break
    else:  
        print("Invalid option.")
