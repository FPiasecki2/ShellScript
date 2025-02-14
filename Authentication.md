using System;
using System.Collections.Generic;

class Program {
    static Dictionary<string, string> users = new Dictionary<string, string>();

    static void Main() {
        while (true) {
            Console.WriteLine("1. Register\n2. Login\n3. Exit");
            string choice = Console.ReadLine();

            if (choice == "1") {
                RegisterUser();
            } else if (choice == "2") {
                LoginUser();
            } else if (choice == "3") {
                break;
            } else {
                Console.WriteLine("Invalid option.");
            }
        }
    }

    static void RegisterUser() {
        Console.Write("Enter username: ");
        string username = Console.ReadLine();
        Console.Write("Enter password: ");
        string password = Console.ReadLine();
        users[username] = password;
        Console.WriteLine("User registered!");
    }

    static void LoginUser() {
        Console.Write("Enter username: ");
        string username = Console.ReadLine();
        Console.Write("Enter password: ");
        string password = Console.ReadLine();

        if (users.ContainsKey(username) && users[username] == password) {
            Console.WriteLine("Login successful!");
        } else {
            Console.WriteLine("Invalid credentials.");
        }
    }
}
