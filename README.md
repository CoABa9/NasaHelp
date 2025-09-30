# NasaHelp
To help everyone
The idea is that an application which helps staff members have all informations at all time. The information which NSAS has is abundend. It is not possible for people  to remeber every bit of information. This application helps in make sure that information is always asses. 
GitHub – For version control, collaboration, and project management.
Markdown (README, docs) – For documentation.
Java (basic web app prototype) – To create a simple, interactive interface.

Open the index.html file in any modern web browser.
Use the search bar or navigation menu to explore categories of NASA information.

import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

public class NasaInfoHub {
    public static void main(String[] args) {
        // Store information in a map (like a mini database)
        Map<String, String> infoDatabase = new HashMap<>();
        infoDatabase.put("Apollo 11", "First successful Moon landing mission, 1969.");
        infoDatabase.put("James Webb Telescope", "NASA's most advanced space telescope, launched 2021.");
        infoDatabase.put("ISS", "International Space Station, a collaborative orbital research facility.");
        infoDatabase.put("Mars Rover Perseverance", "Exploring Mars since 2021, searching for signs of ancient life.");
        infoDatabase.put("Artemis Program", "NASA program to return humans to the Moon by mid-2020s.");

        Scanner scanner = new Scanner(System.in);
        System.out.println("=== Welcome to NASA InfoHub ===");
        System.out.println("This tool helps staff access important information anytime.\n");

        while (true) {
            System.out.println("Choose an option:");
            System.out.println("1. View all information");
            System.out.println("2. Search for information");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");
            String choice = scanner.nextLine();

            if (choice.equals("1")) {
                System.out.println("\n--- All Information ---");
                for (String key : infoDatabase.keySet()) {
                    System.out.println(key + ": " + infoDatabase.get(key));
                }
                System.out.println();
            } else if (choice.equals("2")) {
                System.out.print("\nEnter topic name to search: ");
                String topic = scanner.nextLine();
                if (infoDatabase.containsKey(topic)) {
                    System.out.println(topic + ": " + infoDatabase.get(topic) + "\n");
                } else {
                    System.out.println("Sorry, no information found for: " + topic + "\n");
                }
            } else if (choice.equals("3")) {
                System.out.println("Exiting NASA InfoHub. Stay curious!");
                break;
            } else {
                System.out.println("Invalid choice. Please try again.\n");
            }
        }
        scanner.close();
    }
}
