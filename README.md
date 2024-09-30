# Question-Two-
// runApplication class

/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package runapplication;

import java.util.Scanner;

/**
 *
 * @author ammaa
 */
public class RunApplication {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
       
        Scanner scanner = new Scanner(System.in);

        // Input the vehicle type, city and the number of accidents
        System.out.print("Enter the vehicle type: ");
        String vehicleType = scanner.nextLine();

        System.out.print("Enter the city name: ");
        String cityName = scanner.nextLine();
        
        System.out.println("Enter the number of accidents that occured: ");
        int numberOfAccidents = scanner.nextInt();

        // Prompt the user to create an instance of the RoadAccidents class and print the report
         RoadAccidents roadAccidents = new RoadAccidents(vehicleType, cityName, numberOfAccidents);

        // Print the report
        roadAccidents.printRoadAccidentReport();

    }
}

// Abstract Class

/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package runapplication;

/**
 *
 * @author ammaa
 */
public abstract class RoadAccidents implements IRoadAccidents{
    
    // Declare variables
    String vehicleType;
    String cityName;
    int numberOfAccidents;

    // Create Get Methods to get vehicle types, city and number of accidents
    public String getVehicleType() {
        return vehicleType;
    }

    public String getCityName() {
        return cityName;
    }

    public int getNumberOfAccidents() {
        return numberOfAccidents;
    }
    
    // Create constructors that accepts the vehicle type, city and number of accidents
    public RoadAccidents(String vehicleType, String city, int numberOfAccidents) {
        this.vehicleType = vehicleType;
        this.cityName = city;
        this.numberOfAccidents = numberOfAccidents;
    }
    
    
    
      
}
        
        
 // interface class
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package runapplication;

/**
 *
 * @author ammaa
 */
public interface IRoadAccidents {
    
    // Declarations
        String getAccidentVehicleType();
        String getCityName();
        int getAccidentTotal();
    }
    
 // RoadAccidentFReportClass
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package runapplication;

/**
 *
 * @author ammaa
 */
public class RoadAccidentReport extends RoadAccidents {

    public RoadAccidentReport(String vehicleType, String city, int numberOfAccidents) {
        super(vehicleType, cityName, numberOfAccidents);
    }
    
    // Create a printAccidentReport method
    public void printAccidentReport() {
        System.out.println("VEHICLE ACCIDENT REPORT");
        System.out.println("*************************");
        System.out.println("VEHICLE TYPE: " + getVehicleType());
        System.out.println("CITY: " + getCityName());
        System.out.println("ACCIDENT TOTAL: " + getNumberOfAccidents());
    }
}

   
