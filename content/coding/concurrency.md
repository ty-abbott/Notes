## Concurrency

- being able to run multiple pieces of code at the same time - Concurrency is one approach to drastically increase the performance of your Python programs.
- Concurrency allows several processes to be completed concurrently, maximizing the utilization of your system’s resources.

### Threading 
- this is used IO operations and when the CPU does not need to be heavily utilized. 

### Python
- to make some concurrent tasks, create threads that can be run and then create stop events that are used to interact with the threads. Essentially
a stop event will trigger when the function in question that is the target of the thread needs to be stopped. See capture_stage.py

This also is a good example 
```
import threading
import time

# Define a function that runs until a specific input
def long_running_task(name, stop_event):
    print(f"Starting task: {name}")
    while not stop_event.is_set():  # This loop will keep running until the stop_event is set
       # print(f"Task {name} is working...")
        time.sleep(2)  # Simulate work by sleeping for 2 seconds
    print(f"Task {name} has stopped.")

# Main function that runs continuously and accepts commands from the user
def main():
    stop_events = {}  # Dictionary to store stop events for each task
    threads = {}      # Dictionary to store threads for each task
    
    while True:
        command = input("Enter command (start/stop/list/exit): ").strip().lower()
        
        if command == 'exit':
            # Stop all threads and exit the program
            print("Exiting program...")
            for stop_event in stop_events.values():
                stop_event.set()  # Stop all running tasks
            for thread in threads.values():
                thread.join()  # Wait for all threads to finish
            break
        
        elif command == 'list':
            # List all currently running tasks
            print("Currently running tasks:")
            for name in threads:
                print(f"  - {name}")
        
        elif command.startswith('start '):
            task_name = command.split(' ', 1)[1]  # Get the task name after "start "
            if task_name in threads:
                print(f"Task {task_name} is already running.")
            else:
                stop_event = threading.Event()  # Create an event to control stopping the thread
                stop_events[task_name] = stop_event
                thread = threading.Thread(target=long_running_task, args=(task_name, stop_event))
                threads[task_name] = thread
                thread.start()
                print(f"Started task: {task_name}")
        
        elif command.startswith('stop '):
            task_name = command.split(' ', 1)[1]  # Get the task name after "stop "
            if task_name in stop_events:
                stop_events[task_name].set()  # Stop the task
                threads[task_name].join()  # Wait for the thread to finish
                del stop_events[task_name]
                del threads[task_name]
                print(f"Stopped task: {task_name}")
            else:
                print(f"No such task: {task_name}")
        
        else:
            print("Unknown command. Available commands: start <name>, stop <name>, list, exit")

if __name__ == '__main__':
    main()

```
