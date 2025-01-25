
---

# Airline Flight Reservation System

## Description
This project is an **Airline Flight Reservation System** that allows users to book, cancel, and modify flight tickets. The system maintains passenger details, seat availability, and provides information about booking and cancellation. It is implemented using a linked list to store the passengers' data and basic functionalities to simulate an airline reservation process.

## Features
1. **Book Ticket**: 
   - Allows users to enter their details and select a seat number.
   - Provides the option to choose a food preference (Veg, Non-Veg, or No Food).
   - Assigns a reservation number for each booking.
   
2. **Cancel Ticket**: 
   - Users can cancel their reservations by entering the reservation number.
   - The system will release the seat and update the seat availability.
   
3. **Change Reservation**:
   - Allows users to change their seat by providing the current seat number.
   - Users can choose a new seat from the available options.
   
4. **Passenger Details**:
   - Users can view their booking details by entering their reservation number.
   - The system will display personal details like name, seat number, and food preference.
   
5. **Get Booking Details**:
   - Shows all the booking information for all passengers.
   - Displays a list of all passengers and their respective reservation details.

## How to Use
1. **Run the program** using your Java development environment.
2. **Menu Options**:
   - The program starts with a welcome screen and a menu with options to perform different operations.
   - Select the desired option from the menu:
     1. Book Ticket
     2. Cancel Ticket
     3. Change Reservation
     4. Passenger Details
     5. Get Booking Details
     6. Exit

3. **Seat Selection**:
   - When booking or changing a reservation, users must choose a seat number.
   - If the seat is already taken, the system will prompt the user to select a different seat.

4. **Food Selection**:
   - During booking, users can select their food preference: Veg, Non-Veg, or No Food.

5. **Exit**: 
   - The system will terminate once you select the Exit option.

## Code Structure

### `Flight` Class
The `Flight` class manages the following:
- **Attributes**:
  - `total_number_of_seats`: Total seats available in the flight (100 seats).
  - `seats[]`: An array representing seat availability.
  - A linked list of passengers that stores each passenger's details.

- **Methods**:
  - `book_ticket()`: Takes user input and books a ticket.
  - `cancel_ticket()`: Cancels a ticket and releases the seat.
  - `change_reservation()`: Allows changing the seat for a reservation.
  - `passenger_details()`: Displays the details of a passenger by reservation number.
  - `get_booking_details()`: Displays all the bookings.

### `Passenger` Structure
The passenger structure stores:
- First name, last name, ID, phone number, food menu selection, seat number, and reservation number.
- A pointer to the next passenger in the linked list.

## Installation

To run this program:
1. Install the latest version of [Java JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Compile the Java code:
   ```bash
   javac FlightReservation.java
   ```
3. Run the compiled Java program:
   ```bash
   java FlightReservation
   ```

## Limitations
- The seat layout in this version is hardcoded to 100 seats.
- The linked list implementation is basic and can be optimized for faster lookups.
- The program does not store data persistently; all bookings are lost when the program terminates.

## Future Enhancements
- Implementing a GUI for better user interaction.
- Adding real-time flight schedules and pricing.
- Storing and retrieving data from a database.

---
