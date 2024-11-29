# Documentation for the To-Do List Application

## Overview
This project is a simple **To-Do List Application** created using Python's **Tkinter** library. The application allows users to manage a list of tasks by providing options to add, remove, and clear tasks.

---

## Features
1. **Add a Task**: Users can input a task and add it to the list.
2. **Remove a Selected Task**: Users can select a task from the list and remove it.
3. **Clear All Tasks**: Users can clear the entire task list at once.

---

## Components
### 1. **Entry Widget**
   - Used to input tasks.
   - Created using:
     ```python
     entry = tk.Entry(root, width=50)
     ```
   - Positioned at the top of the application.

### 2. **Buttons**
   - **Add Task Button**:
     - Adds a task from the `entry` widget to the `listbox`.
     - Command: `add_task`
     - Code:
       ```python
       add_button = tk.Button(root, text="Add Task", command=add_task)
       ```
   - **Remove Selected Task Button**:
     - Removes the currently selected task in the `listbox`.
     - Command: `remove_task`
     - Code:
       ```python
       remove_button = tk.Button(root, text="Remove Selected Task", command=remove_task)
       ```
   - **Clear All Tasks Button**:
     - Clears all tasks in the `listbox`.
     - Command: `clear_tasks`
     - Code:
       ```python
       clear_button = tk.Button(root, text="Clear All Tasks", command=clear_tasks)
       ```

### 3. **Listbox**
   - Displays the list of tasks.
   - Allows task selection for removal.
   - Created using:
     ```python
     listbox = tk.Listbox(root, width=50, height=10)
     ```

---

## Functions
### 1. `add_task()`
   - Retrieves text from the `entry` widget and adds it to the `listbox`.
   - Clears the `entry` widget after adding the task.
   - Handles empty inputs by skipping the addition.

   ```python
   def add_task():
       task = entry.get()
       if task:
           listbox.insert(tk.END, task)
           entry.delete(0, tk.END)
   ```

### 2. `remove_task()`
   - Removes the currently selected task from the `listbox`.
   - Handles cases where no task is selected by using a `try-except` block.

   ```python
   def remove_task():
       try:
           selected_task_index = listbox.curselection()[0]
           listbox.delete(selected_task_index)
       except IndexError:
           pass
   ```

### 3. `clear_tasks()`
   - Clears all tasks from the `listbox`.

   ```python
   def clear_tasks():
       listbox.delete(0, tk.END)
   ```

---

## Main Application Code
### 1. **Window Setup**
   - The main application window is created using `tk.Tk()` and given a title:
     ```python
     root = tk.Tk()
     root.title("To-Do List Application")
     ```

### 2. **Widget Layout**
   - Widgets are added to the window using `.pack()` with optional padding for spacing.

---

## How to Run the Application
1. Ensure Python is installed on your system.
2. Save the code in a `.py` file (e.g., `todo_list.py`).
3. Run the file using:
   ```
   python todo_list.py
   ```
4. Interact with the application window to manage your to-do list.

---

## Possible Enhancements
1. **Save and Load Tasks**: Add functionality to save tasks to a file and load them back on reopening the application.
2. **Edit Tasks**: Allow editing of existing tasks in the `listbox`.
3. **Task Prioritization**: Enable reordering or highlighting of high-priority tasks.
4. **Styling**: Improve the user interface with custom fonts, colors, and layouts.

---

## Conclusion
This project demonstrates the use of **Tkinter** to build a graphical user interface for managing tasks. It is simple, effective, and serves as a great foundation for further enhancements.
