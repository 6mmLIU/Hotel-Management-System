# Hotel Management System

This project is a simple Hotel Management System written in C++. It includes functionalities such as booking rooms, checking in, checking out, and inquiring room status. 

## Features

- **Room Booking**: Allows customers to book rooms based on room standards.
- **Check-In**: Handles customer check-in, either with a prior booking or without.
- **Check-Out**: Manages customer check-out, including billing based on actual stay duration.
- **Inquiry**: Provides information on room status (available, booked, occupied) and customer details.

## Room Standards

There are 80 rooms categorized into four standards:
1. **Single Room**: ¥150 per day
2. **Double Room**: ¥200 per day
3. **Standard Room**: ¥300 per day
4. **Presidential Suite**: ¥600 per day

## Usage

### Initialization

1. **Initialize Rooms**: The `initial_room()` function initializes the details of 80 rooms, categorized into four standards.
2. **Welcome Screen**: The `welcome()` function prompts for user login. The correct username and password are "000" and "666666" respectively.

### Main Functions

- **Book Room**: The `book_room()` function allows customers to book rooms by selecting the room standard and number of days.
- **Check In**: The `check_in()` function handles customer check-in, charging based on the selected room standard and number of days.
- **Check Out**: The `check_out()` function manages customer check-out, adjusting the bill based on actual stay duration.
- **Inquiry**: The `inquire()` function provides room status information and customer details.

### Workflow

1. Start the program.
2. Login with the correct username and password.
3. Select the desired service from booking, check-in, check-out, or inquiry.
4. Follow the prompts to complete the selected service.
5. To continue using the system, press "1". To exit, press "2".

## Code Structure

### Classes

- **Customer**: Manages customer information including name, ID, room number, days of stay, and prepaid amount.

### Functions

- **initial_room()**: Initializes room information.
- **welcome()**: Handles user login.
- **enter()**: Directs to the appropriate service based on user input.
- **book_room()**: Books a room for a customer.
- **check_in()**: Manages customer check-in process.
- **check_out()**: Manages customer check-out process.
- **inquire()**: Provides room and customer information based on the query.

## Example

```cpp
#include <iostream>
#include <cstring>

using namespace std;

// Function declarations
void initial_room();
void welcome();
void enter();
void book_room();
void check_in();
void check_out();
void inquire();

int i = 0;

struct Room {
    int number;
    int dank;
    int price;
    int state;
};

class Customer {
public:
    Customer();
    void set_name(const char* n) { strcpy_s(name, n); }
    void set_ID(const char* p) { strcpy_s(ID, p); }
    void set_room_number(int n) { room_number = n; }
    void set_day(int d) { day = d; }
    void set_prepaid(int p) { prepaid = p; }
    const char* get_name() { return name; }
    const char* get_ID() { return ID; }
    int get_room_number() { return room_number; }
    int get_day() { return day; }
    int get_prepaid() { return prepaid; }
    virtual ~Customer();

private:
    char name[10], ID[19];
    int room_number;
    int prepaid;
    int change;
    int day;
};

// Function definitions
// ...

int main() {
    char choice = '1';
    initial_room();
    welcome();

    while (choice == '1') {
        enter();
        cout << endl;
        cout << "继续使用本系统请按\"1\", 退出请按\"2\"!  ";
        cin >> choice;
        cout << endl;
    }

    return 0;
}

// Implementations of functions
// ...
