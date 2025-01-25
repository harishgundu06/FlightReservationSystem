import java.util.Scanner;
import java.util.LinkedList;

class Flight {
    private static final int TOTAL_NUMBER_OF_SEATS = 100;
    private static int[] seats = new int[TOTAL_NUMBER_OF_SEATS];
    private static int reserveSeats = 1000;
    private static int cancelTickets = 0;
    private LinkedList<Passenger> passengers;

    public Flight() {
        passengers = new LinkedList<>();
    }

    private static class Passenger {
        String firstName;
        String lastName;
        String id;
        String phoneNumber;
        String foodMenu;
        int seatNumber;
        int reservationNumber;

        Passenger(String firstName, String lastName, String id, String phoneNumber, String foodMenu, int seatNumber, int reservationNumber) {
            this.firstName = firstName;
            this.lastName = lastName;
            this.id = id;
            this.phoneNumber = phoneNumber;
            this.foodMenu = foodMenu;
            this.seatNumber = seatNumber;
            this.reservationNumber = reservationNumber;
        }
    }

    public void bookTicket() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your first name: ");
        String firstName = scanner.nextLine();
        
        System.out.print("Enter your last name: ");
        String lastName = scanner.nextLine();
        
        System.out.print("Enter your ID: ");
        String id = scanner.nextLine();

        System.out.print("Enter your phone number: ");
        String phoneNumber = scanner.nextLine();

        int seatNumber;
        while (true) {
            System.out.print("Enter the seat number (1-100): ");
            seatNumber = scanner.nextInt();
            if (seatNumber > 0 && seatNumber <= TOTAL_NUMBER_OF_SEATS && seats[seatNumber - 1] == 0) {
                seats[seatNumber - 1] = -1;
                break;
            } else {
                System.out.println("Invalid or already booked seat. Please try again.");
            }
        }

        System.out.println("Enter your food choice preference:");
        System.out.println("1. Veg");
        System.out.println("2. Non-Veg");
        System.out.println("3. No Food");
        String foodMenu;
        int choice;
        while (true) {
            System.out.print("Your choice: ");
            choice = scanner.nextInt();
            if (choice == 1) {
                foodMenu = "Veg";
                break;
            } else if (choice == 2) {
                foodMenu = "Non-Veg";
                break;
            } else if (choice == 3) {
                foodMenu = "No Food";
                break;
            } else {
                System.out.println("Invalid choice, please try again.");
            }
        }

        reserveSeats++;
        Passenger passenger = new Passenger(firstName, lastName, id, phoneNumber, foodMenu, seatNumber, reserveSeats);
        passengers.add(passenger);

        System.out.println("Your reservation number is: " + reserveSeats);
    }

    public void cancelTicket() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your reservation number: ");
        int reservationNumber = scanner.nextInt();

        Passenger passengerToRemove = null;
        for (Passenger passenger : passengers) {
            if (passenger.reservationNumber == reservationNumber) {
                passengerToRemove = passenger;
                break;
            }
        }

        if (passengerToRemove != null) {
            passengers.remove(passengerToRemove);
            seats[passengerToRemove.seatNumber - 1] = 0;
            cancelTickets++;
            System.out.println("Ticket successfully cancelled.");
        } else {
            System.out.println("Reservation number not found.");
        }
    }

    public void changeReservation() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your current seat number: ");
        int currentSeatNumber = scanner.nextInt();

        Passenger currentPassenger = null;
        for (Passenger passenger : passengers) {
            if (passenger.seatNumber == currentSeatNumber) {
                currentPassenger = passenger;
                break;
            }
        }

        if (currentPassenger == null) {
            System.out.println("No reservation found for the entered seat number.");
            return;
        }

        System.out.println("Available seats: ");
        for (int i = 0; i < TOTAL_NUMBER_OF_SEATS; i++) {
            if (seats[i] == 0) {
                System.out.print((i + 1) + " ");
            }
        }
        System.out.println();

        int newSeatNumber;
        while (true) {
            System.out.print("Enter the new seat number: ");
            newSeatNumber = scanner.nextInt();
            if (newSeatNumber > 0 && newSeatNumber <= TOTAL_NUMBER_OF_SEATS && seats[newSeatNumber - 1] == 0) {
                seats[currentPassenger.seatNumber - 1] = 0;
                currentPassenger.seatNumber = newSeatNumber;
                seats[newSeatNumber - 1] = -1;
                break;
            } else {
                System.out.println("Invalid or already booked seat. Please try again.");
            }
        }
    }

    public void passengerDetails() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your reservation number: ");
        int reservationNumber = scanner.nextInt();

        for (Passenger passenger : passengers) {
            if (passenger.reservationNumber == reservationNumber) {
                System.out.println("Reservation Number: " + passenger.reservationNumber);
                System.out.println("First Name: " + passenger.firstName);
                System.out.println("Last Name: " + passenger.lastName);
                System.out.println("ID: " + passenger.id);
                System.out.println("Phone Number: " + passenger.phoneNumber);
                System.out.println("Seat Number: " + passenger.seatNumber);
                System.out.println("Food Menu: " + passenger.foodMenu);
                return;
            }
        }

        System.out.println("Reservation number not found.");
    }

    public void getBookingDetails() {
        System.out.println("Reservation Number | First Name | Last Name | ID | Phone Number | Seat Number | Food Menu");
        for (Passenger passenger : passengers) {
            System.out.printf("%d | %s | %s | %s | %s | %d | %s\n",
                    passenger.reservationNumber, passenger.firstName, passenger.lastName,
                    passenger.id, passenger.phoneNumber, passenger.seatNumber, passenger.foodMenu);
        }
    }
}

public class FlightReservationSystem {
    public static void main(String[] args) {
        Flight flight = new Flight();
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            System.out.println("\n|---------------------------|");
            System.out.println("| Airline Reservation Menu |");
            System.out.println("|---------------------------|");
            System.out.println("1. Book Ticket");
            System.out.println("2. Cancel Ticket");
            System.out.println("3. Change Reservation");
            System.out.println("4. Passenger Details");
            System.out.println("5. Get Booking Details");
            System.out.println("6. Exit");
            System.out.print("Enter your choice: ");

            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    flight.bookTicket();
                    break;
                case 2:
                    flight.cancelTicket();
                    break;
                case 3:
                    flight.changeReservation();
                    break;
                case 4:
                    flight.passengerDetails();
                    break;
                case 5:
                    flight.getBookingDetails();
                    break;
                case 6:
                    System.out.println("Exiting system. Thank you!");
                    return;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }
}
