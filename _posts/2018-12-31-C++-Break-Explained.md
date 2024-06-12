
## C++ Break Statement

When dealing with any kind of loop in C++, chances are you will come across the **break** statement. Sometimes there is confusion about when **break** should be used, especially among people starting to learn C++.

In this post, I will try to clarify and illustrate proper usage and pitfalls of the `break` statement.

## C++ break in loops

I will start with the easier to describe the `break` statement. Its function is simply to **exit a program loop or switch statement immediately**.

Let's see an example with a while loop:

```cpp
#include <iostream>

int main() {
    // Count from 0 to 100 but exit as soon as the counter reaches 10
    int myNumber = 0;

    while (myNumber < 100) {
        std::cout << "This is inside the loop, value is " << myNumber << std::endl;

        // Increment
        myNumber++;

        if (myNumber == 10) {
            std::cout << "Value is " << myNumber << " - Exiting now!" << std::endl;
            break;
        }

        std::cout << "Value is " << myNumber << std::endl;
    }

    std::cout << "This is outside the loop" << std::endl;
    return 0;
}
```

The above code will start incrementing the `myNumber` variable. When it has a value of `10`, the while loop will be stopped and the `This is outside the loop` line will be printed.

The same can also be applied to a `for` loop like this:

```cpp
#include <iostream>
#include <vector>
#include <string>

int main() {
    // Users list
    std::vector<std::string> userList = {"user1", "user2", "user3"};

    for (const auto& user : userList) {
        std::cout << "Processing user " << user << std::endl;

        if (user != "user2") {
            std::cout << "Updating user properties!" << std::endl;
        } else {
            std::cout << "Exiting loop now!" << std::endl;
            break;
        }
    }

    std::cout << "This is outside the loop" << std::endl;
    return 0;
}
```

In the above example, we are cycling through elements of a vector and taking some actions. When the username is `user2`, the loop will be exited and the `This is outside the loop` line will be printed.

## C++ break in switch statements

The `break` statement is also used in `switch` statements to exit the switch case once a particular case has been executed:

```cpp
#include <iostream>

int main() {
    int number = 2;

    switch (number) {
        case 1:
            std::cout << "Number is 1" << std::endl;
            break;
        case 2:
            std::cout << "Number is 2" << std::endl;
            break;
        case 3:
            std::cout << "Number is 3" << std::endl;
            break;
        default:
            std::cout << "Number is not 1, 2, or 3" << std::endl;
            break;
    }

    std::cout << "This is outside the switch" << std::endl;
    return 0;
}
```

In the above example, based on the value of `number`, the corresponding case is executed, and then the `break` statement ensures that the program exits the switch block.

By using the `break` statement correctly, you can control the flow of your loops and switch statements effectively in C++.
