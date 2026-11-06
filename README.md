# College Management System
# Based on Waterfall Model
# Software Engineering PBL Project

students = {}

# Phase 1: Requirement Analysis
# System requirements:
# Student details, attendance, fees and marks management.

# Phase 2: System Design
# Menu-based system for managing student records.

# Phase 3: Implementation
# Writing Python code.

def add_student():
    uid = input("Enter Student ID: ")
    name = input("Enter Student Name: ")
    course = input("Enter Course: ")

    students[uid] = {
        "Name": name,
        "Course": course,
        "Attendance": 0,
        "Fees": "Pending",
        "Marks": 0
    }

    print("Student added successfully!")


def view_students():
    if not students:
        print("No student records found.")
        return

    for uid, details in students.items():
        print("\nStudent ID:", uid)
        for key, value in details.items():
            print(key + ":", value)


def search_student():
    uid = input("Enter Student ID to search: ")

    if uid in students:
        print("Student Details:", students[uid])
    else:
        print("Student not found!")


def mark_attendance():
    uid = input("Enter Student ID: ")

    if uid in students:
        students[uid]["Attendance"] += 1
        print("Attendance marked successfully!")
    else:
        print("Student not found!")


def update_fees():
    uid = input("Enter Student ID: ")

    if uid in students:
        students[uid]["Fees"] = "Paid"
        print("Fee status updated!")
    else:
        print("Student not found!")


def add_marks():
    uid = input("Enter Student ID: ")

    if uid in students:
        marks = int(input("Enter Student Marks: "))
        students[uid]["Marks"] = marks
        print("Marks added successfully!")
    else:
        print("Student not found!")


# Phase 4: Testing
# Testing different functions and checking errors.

# Phase 5: Deployment
# Making the system available to college staff.

# Phase 6: Maintenance
# Updating records and fixing errors when required.


# Main Program

while True:
    print("\n===== COLLEGE MANAGEMENT SYSTEM =====")
    print("1. Add Student")
    print("2. View All Students")
    print("3. Search Student")
    print("4. Mark Attendance")
    print("5. Update Fees")
    print("6. Add Marks")
    print("7. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_student()

    elif choice == "2":
        view_students()

    elif choice == "3":
        search_student()

    elif choice == "4":
        mark_attendance()

    elif choice == "5":
        update_fees()

    elif choice == "6":
        add_marks()

    elif choice == "7":
        print("Thank you for using College Management System!")
        break

    else:
        print("Invalid choice! Please try again.")
