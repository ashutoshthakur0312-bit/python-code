import os
def file():
    name=input("enter file name with extension:")
    with open(name, "w") as f:
        print("file created successfully!")
def write():
    name=input("enter file name with extension:")
    data=input("enter data to write in file:")
    with open(name, "w") as f:
        f.write(data)
        print("data written to file successfully!")
def append():
    name=input("enter file name with extension:")
    data=input("enter data to append in file:")
    with open(name, "a") as f:
        f.write("\n"+data)
        print("data appended to file successfully!")
def read():
    name=input("enter file name with extension:")
    if os.path.exists(name):
        with open(name, "r") as f:
            content=f.read()
            print("file content:")
            print(content)
    else:
        print("file does not exist!")
def delete():
    name=input("enter file name with extension:")
    if os.path.exists(name):
        os.remove(name)
        print("file deleted successfully!")
    else:
        print("file does not exist!")
def main():
    while True:
        print("1. Create a new file")
        print("2. Write to a file")
        print("3. Append to a file")
        print("4. Read a file")
        print("5. Delete a file")
        print("6. Exit")
        choice=int(input("Enter your choice:"))
        if choice==1:
            file()
        elif choice==2:
            write()
        elif choice==3:
            append()
        elif choice==4:
            read()
        elif choice==5:
            delete()
        elif choice==6:
            print("Exiting...")
            break
        else:
            print("Invalid choice! Please try again.")

main()
