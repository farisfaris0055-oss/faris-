# Student Attendance Management System

attendance = {}

while True:
    print("\n===== Student Attendance System =====")
    print("1. Add Student")
    print("2. Mark Attendance")
    print("3. View Attendance")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        name = input("Enter student name: ")
        attendance[name] = []
        print("Student added successfully!")

    elif choice == "2":
        name = input("Enter student name: ")

        if name in attendance:
            status = input("Enter attendance (P for Present / A for Absent): ").upper()

            if status == "P":
                attendance[name].append("Present")
                print("Attendance marked as Present.")
            elif status == "A":
                attendance[name].append("Absent")
                print("Attendance marked as Absent.")
            else:
                print("Invalid attendance status!")
        else:
            print("Student not found!")

    elif choice == "3":
        if len(attendance) == 0:
            print("No student records available.")
        else:
            print("\nAttendance Report")
            for student, records in attendance.items():
                present_count = records.count("Present")
                absent_count = records.count("Absent")
                print(f"\nStudent: {student}")
                print(f"Present Days: {present_count}")
                print(f"Absent Days: {absent_count}")

    elif choice == "4":
        print("Exiting Attendance System...")
        break

    else:
        print("Invalid choice! Please try again.")
