

https://github.com/user-attachments/assets/b9a483a2-76ad-4f5a-9697-afdc25b644b7





# Wi-Fi Jammer System

## Team Details

| Name | Student ID | Role |
|------|------------|------|
| Bilal Saleem   | 001 | Developer / Team Leader |
| Sohaib Asghar  | 016 | Developer               |

---

## Problem Statement

Wireless networks can experience interference that affects their performance and
connectivity. Understanding the basic concept of wireless interference is
important for Electrical Engineering and Computer Science students.

This project is an educational **Wi-Fi Jammer Simulation** developed to
demonstrate the concept of wireless interference in a safe software environment.
It does not perform real-world Wi-Fi jamming or interfere with actual networks.

---

## Solution

The project provides a simple simulation where the user can select different
simulation options and observe how interference can affect a hypothetical
wireless connection.

The simulation focuses on understanding:

- Wireless signal interference
- Signal strength
- Connection status
- Basic jammer concepts
- Effect of interference on communication

---

## Tech Stack

- **Programming Language:** C++
- **IDE:** Dev-C++
- **Platform:** Windows
- **Type:** Console-based educational simulation

---

## Key Features

- Simple and easy-to-use console interface
- Menu-based options
- Simulated Wi-Fi signal strength
- Simulated interference
- Connection status display
- Beginner-friendly C++ implementation
- No real wireless transmission
- Safe for educational demonstration

---

## Installation

### Step 1: Install Dev-C++

Install Dev-C++ on your computer.

### Step 2: Clone the Repository

Open Command Prompt or Terminal and run:

```bash
git clone YOUR-GITHUB-REPOSITORY-LINK
CODE
#include <iostream>
#include <string>
using namespace std;

// Function prototypes
void showMenu();
void startJammer(int channel, int power);
void stopJammer();
void showStatus(bool status, int channel, int power);
void channelScanner();
void showReport(bool status, int channel, int power);

int main()
{
    int choice;
    int channel = 6;
    int power = 50;
    bool jammerStatus = false;

    cout << "========================================" << endl;
    cout << "          WIFI JAMMER SYSTEM" << endl;
    cout << "========================================" << endl;
    cout << "       COMPUTER PROGRAMMING LAB" << endl;
    cout << "========================================" << endl;

    do
    {
        showMenu();

        cout << "Enter your choice: ";
        cin >> choice;

        switch(choice)
        {
            case 1:
                jammerStatus = true;
                startJammer(channel, power);
                break;

            case 2:
                jammerStatus = false;
                stopJammer();
                break;

            case 3:
                cout << "\nEnter Wi-Fi Channel (1-13): ";
                cin >> channel;

                if(channel >= 1 && channel <= 13)
                {
                    cout << "Channel changed successfully." << endl;
                }
                else
                {
                    cout << "Invalid channel!" << endl;
                    channel = 6;
                }
                break;

            case 4:
                cout << "\nEnter Power Level (1-100): ";
                cin >> power;

                if(power >= 1 && power <= 100)
                {
                    cout << "Power level set to "
                         << power << "%" << endl;
                }
                else
                {
                    cout << "Invalid power level!" << endl;
                    power = 50;
                }
                break;

            case 5:
                showStatus(jammerStatus, channel, power);
                break;

            case 6:
                channelScanner();
                break;

            case 7:
                showReport(jammerStatus, channel, power);
                break;

            case 8:
                cout << "\nProgram terminated." << endl;
                break;

            default:
                cout << "\nInvalid choice! Try again." << endl;
        }

    } while(choice != 8);

    return 0;
}


// Menu Function
void showMenu()
{
    cout << "\n\n========================================" << endl;
    cout << "               MAIN MENU" << endl;
    cout << "========================================" << endl;

    cout << "1. Start Jammer" << endl;
    cout << "2. Stop Jammer" << endl;
    cout << "3. Select Wi-Fi Channel" << endl;
    cout << "4. Set Power Level" << endl;
    cout << "5. Show Status" << endl;
    cout << "6. Channel Scanner" << endl;
    cout << "7. Generate Report" << endl;
    cout << "8. Exit" << endl;

    cout << "========================================" << endl;
}


// Start Function
void startJammer(int channel, int power)
{
    cout << "\n----------------------------------------" << endl;
    cout << "[+] JAMMER STARTED" << endl;
    cout << "[+] Channel     : " << channel << endl;
    cout << "[+] Power Level : " << power << "%" << endl;
    cout << "[+] Status      : ACTIVE" << endl;
    cout << "[!] LAB DEMONSTRATION MODE" << endl;
    cout << "----------------------------------------" << endl;
}


// Stop Function
void stopJammer()
{
    cout << "\n----------------------------------------" << endl;
    cout << "[-] JAMMER STOPPED" << endl;
    cout << "[-] Status : INACTIVE" << endl;
    cout << "----------------------------------------" << endl;
}


// Status Function
void showStatus(bool status, int channel, int power)
{
    cout << "\n========================================" << endl;
    cout << "             SYSTEM STATUS" << endl;
    cout << "========================================" << endl;

    if(status == true)
        cout << "Jammer Status : ACTIVE" << endl;
    else
        cout << "Jammer Status : INACTIVE" << endl;

    cout << "Channel       : " << channel << endl;
    cout << "Power Level   : " << power << "%" << endl;

    cout << "========================================" << endl;
}


// Channel Scanner
void channelScanner()
{
    cout << "\n========================================" << endl;
    cout << "           CHANNEL SCANNER" << endl;
    cout << "========================================" << endl;

    for(int i = 1; i <= 13; i++)
    {
        cout << "Channel " << i << " : Available" << endl;
    }

    cout << "========================================" << endl;
}


// Report Function
void showReport(bool status, int channel, int power)
{
    cout << "\n========================================" << endl;
    cout << "             FINAL REPORT" << endl;
    cout << "========================================" << endl;

    cout << "Project Name : Wi-Fi Jammer System" << endl;

    if(status == true)
        cout << "Status       : ACTIVE" << endl;
    else
        cout << "Status       : INACTIVE" << endl;

    cout << "Channel      : " << channel << endl;
    cout << "Power Level  : " << power << "%" << endl;

    cout << "----------------------------------------" << endl;
    cout << "Programming Concepts Used:" << endl;
    cout << "1. Variables" << endl;
    cout << "2. Functions" << endl;
    cout << "3. If-Else" << endl;
    cout << "4. Switch Statement" << endl;
    cout << "5. Do-While Loop" << endl;
    cout << "6. For Loop" << endl;
    cout << "7. User Input/Output" << endl;

    cout << "========================================" << endl;
}
