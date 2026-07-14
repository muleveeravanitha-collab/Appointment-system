# Appointment-system
appointments = []

def book_appointment():
    print("\n--- Book Appointment ---")

    name = input("Enter Patient Name: ")
    age = input("Enter Age: ")
    gender = input("Enter Gender: ")
    doctor = input("Enter Doctor Name: ")
    date = input("Enter Appointment Date (DD/MM/YYYY): ")
    time = input("Enter Appointment Time: ")

    appointment_id = len(appointments) + 1

    appointment = {
        "ID": appointment_id,
        "Name": name,
        "Age": age,
        "Gender": gender,
        "Doctor": doctor,
        "Date": date,
        "Time": time
    }

    appointments.append(appointment)

    print("\nAppointment Booked Successfully!")
    print("Appointment ID:", appointment_id)


def view_appointments():
    print("\n===== Patient Appointments =====")

    if len(appointments) == 0:
        print("No appointments booked.")
        return

    for appointment in appointments:
        print("-----------------------------")
        print("Appointment ID:", appointment["ID"])
        print("Name:", appointment["Name"])
        print("Age:", appointment["Age"])
        print("Gender:", appointment["Gender"])
        print("Doctor:", appointment["Doctor"])
        print("Date:", appointment["Date"])
        print("Time:", appointment["Time"])


while True:
    print("\n===== Automated Patient Booking System =====")
    print("1. Book Appointment")
    print("2. View Appointments")
    print("3. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        book_appointment()

    elif choice == "2":
        view_appointments()

    elif choice == "3":
        print("Thank you for using the system.")
        break

    else:
        print("Invalid choice! Please try again.")
