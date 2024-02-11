### Question 1

```cpp
#include <iostream>
using namespace std;

void printSpiral(int m, int n) {
    int matrix[m][n];
    int top = 0, bottom = m - 1, left = 0, right = n - 1;
    int val = 1;

    while (top <= bottom && left <= right) {
        for (int i = left; i <= right; i++)
            matrix[top][i] = val++;
        top++;

        for (int i = top; i <= bottom; i++)
            matrix[i][right] = val++;
        right--;

        if (top <= bottom) {
            for (int i = right; i >= left; i--)
                matrix[bottom][i] = val++;
            bottom--;
        }

        if (left <= right) {
            for (int i = bottom; i >= top; i--)
                matrix[i][left] = val++;
            left++;
        }
    }

    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++)
            cout << matrix[i][j] << " ";
        cout << endl;
    }
}

int main() {
    int m = 3, n = 4;
    printSpiral(m, n);
    return 0;
}
```

### Question 2

```cpp
#include <iostream>
using namespace std;

int reverseInteger(int n) {
    bool negative = false;
    if (n < 0) {
        negative = true;
        n = -n;
    }

    int reversed = 0;
    while (n > 0) {
        reversed = reversed * 10 + n % 10;
        n /= 10;
    }

    return negative ? -reversed : reversed;
}

int main() {
    int num = 12345;
    cout << "Reversed: " << reverseInteger(num) << endl;
    return 0;
}
```

### Question 3

```cpp
#include <iostream>
#include <string>
using namespace std;

class BankAccount {
private:
    int accountNumber;
    string holderName;
    double balance;

public:
    BankAccount(int accNum, string name, double initialBalance) : accountNumber(accNum), holderName(name), balance(initialBalance) {}

    void deposit(double amount) {
        balance += amount;
    }

    bool withdraw(double amount) {
        if (balance >= amount) {
            balance -= amount;
            return true;
        }
        return false;
    }

    void display() {
        cout << "Account Number: " << accountNumber << endl;
        cout << "Holder's Name: " << holderName << endl;
        cout << "Balance: " << balance << endl;
    }

    friend void transferFunds(BankAccount& from, BankAccount& to, double amount);
};

void transferFunds(BankAccount& from, BankAccount& to, double amount) {
    if (from.balance >= amount) {
        from.balance -= amount;
        to.balance += amount;
        cout << "Transfer successful!" << endl;
    } else {
        cout << "Insufficient balance for transfer." << endl;
    }
}

int main() {
    BankAccount acc1(12345, "John Doe", 1000);
    BankAccount acc2(54321, "Jane Smith", 500);

    acc1.display();
    cout << endl;
    acc2.display();
    cout << endl;

    transferFunds(acc1, acc2, 300);

    acc1.display();
    cout << endl;
    acc2.display();

    return 0;
}
```

### Question 4

```cpp
#include <iostream>
#include <string>
using namespace std;

class Task {
private:
    int taskId;
    string description;
    string status;

public:
    Task(int id, string desc, string stat) : taskId(id), description(desc), status(stat) {}

    void updateStatus(string newStatus) {
        status = newStatus;
    }

    void display() {
        cout << "Task ID: " << taskId << endl;
        cout << "Description: " << description << endl;
        cout << "Status: " << status << endl;
    }

    friend void assignTask(Task& task, string user);
};

void assignTask(Task& task, string user) {
    // Logic for assigning task to user
    cout << "Task assigned to " << user << endl;
}

int main() {
    Task task1(1, "Implement feature X", "In progress");
    Task task2(2, "Write documentation", "Pending");

    task1.display();
    cout << endl;
    task2.display();
    cout << endl;

    task1.updateStatus("Completed");

    assignTask(task2, "John");

    task1.display();
    cout << endl;
    task2.display();

    return 0;
}
```

### Question 5

```cpp
#include <iostream>
#include <filesystem>
using namespace std;
namespace fs = std::filesystem;

class DirectorySizeCalculator {
private:
    uintmax_t totalSize;

public:
    DirectorySizeCalculator() : totalSize(0) {}

    void calculateDirectorySize(const fs::path& directory) {
        for (const auto& entry : fs::recursive_directory_iterator(directory)) {
            if (fs::is_regular_file(entry)) {
                totalSize += fs::file_size(entry);
            }
        }
    }

    uintmax_t getTotalSize() const {
        return totalSize;
    }
};

int main() {
    DirectorySizeCalculator calculator;
    calculator.calculateDirectorySize("../");
    cout << "Total size of directory and subdirectories: " << calculator.getTotalSize() << " bytes" << endl;
    return 0;
}
```