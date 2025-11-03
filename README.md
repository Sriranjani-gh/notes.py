# notes.py`
import datetime

def add_note():
    note = input("hello: ")
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    with open("notes.txt", "a") as f:
        f.write(f"[{timestamp}] {note}\n")
    print("✅ Note saved!")

def view_notes():
    try:
        with open("notes.txt", "r") as f:
            print("\n--- Your Notes ---")
            print(f.read())
    except FileNotFoundError:
        print("No notes yet!")

print("1) Add Note")
print("2) View Notes")
choice = input("Choose: ")

if choice == "1":
    add_note()
elif choice == "2":
    view_notes()
else:
    print("Invalid input!")
