#include <iostream>
#include <vector>
#include <string>

using namespace std;

struct Task {
    string name;
    bool completed;

    Task(string n) : name(n), completed(false) {}
};

class ToDoList {
private:
    vector<Task> tasks;

public:
    void addTask(const string& taskName) {
        tasks.push_back(Task(taskName));
    }

    void viewTasks() {
        if (tasks.empty()) {
            cout << "No tasks to display." << endl;
        } else {
            cout << "Tasks:" << endl;
            for (size_t i = 0; i < tasks.size(); ++i) {
                cout << i + 1 << ". " << tasks[i].name << " - " << (tasks[i].completed ? "Completed" : "Pending") << endl;
            }
        }
    }

    void markTaskAsCompleted(size_t index) {
        if (index >= 1 && index <= tasks.size()) {
            tasks[index - 1].completed = true;
            cout << "Task marked as completed." << endl;
        } else {
            cout << "Invalid task index." << endl;
        }
    }

    void removeTask(size_t index) {
        if (index >= 1 && index <= tasks.size()) {
            tasks.erase(tasks.begin() + index - 1);
            cout << "Task removed." << endl;
        } else {
            cout << "Invalid task index." << endl;
        }
    }
};

int main() {
    ToDoList todoList;
    int choice;
    string taskName;
    size_t index;

    do {
        cout << "\n1. Add Task\n2. View Tasks\n3. Mark Task as Completed\n4. Remove Task\n0. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter task name: ";
                cin.ignore();
                getline(cin, taskName);
                todoList.addTask(taskName);
                break;
            case 2:
                todoList.viewTasks();
                break;
            case 3:
                cout << "Enter index of task to mark as completed: ";
                cin >> index;
                todoList.markTaskAsCompleted(index);
                break;
            case 4:
                cout << "Enter index of task to remove: ";
                cin >> index;
                todoList.removeTask(index);
                break;
            case 0:
                cout << "Exiting program." << endl;
                break;
            default:
                cout << "Invalid choice. Please try again." << endl;
                break;
        }
    } while (choice != 0);

    return 0;
}
