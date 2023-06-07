# ES2015Classes16.1.12CarOOProject

**Part one, create a class for a vehicle.**
class Vehicle {
  constructor(make, model, year) {
    this.make = make;
    this.model = model;
    this.year = year;
  }

  honk() {
    return "Beep.";
  }
}

// Create a new instance of Vehicle
let myFirstVehicle = new Vehicle("Honda", "Monster Truck", 1999);
console.log(myFirstVehicle.honk()); // Output: "Beep."

**Part two, create a class for a car.**
class Vehicle {
  constructor(make, model, year) {
    this.make = make;
    this.model = model;
    this.year = year;
  }

  honk() {
    return "Beep.";
  }

  toString() {
    return `The vehicle is a ${this.make} ${this.model} from ${this.year}.`;
  }
}

class Car extends Vehicle {
  constructor(make, model, year) {
    super(make, model, year);
    this.numWheels = 4;
  }
}

// Create a new instance of Car
let myFirstCar = new Car("Toyota", "Corolla", 2005);
console.log(myFirstCar.toString()); // Output: "The vehicle is a Toyota Corolla from 2005."
console.log(myFirstCar.honk());     // Output: "Beep."
console.log(myFirstCar.numWheels);  // Output: 4



**Part three, create a class for a Motorcycle.**
class Vehicle {
  constructor(make, model, year) {
    this.make = make;
    this.model = model;
    this.year = year;
  }

  honk() {
    return "Beep.";
  }

  toString() {
    return `The vehicle is a ${this.make} ${this.model} from ${this.year}.`;
  }
}

class Motorcycle extends Vehicle {
  constructor(make, model, year) {
    super(make, model, year);
    this.numWheels = 2;
  }

  revEngine() {
    return "VROOM!!!";
  }
}

// Create a new instance of Motorcycle
let myFirstMotorcycle = new Motorcycle("Honda", "Nighthawk", 2000);
console.log(myFirstMotorcycle.toString());    // Output: "The vehicle is a Honda Nighthawk from 2000."
console.log(myFirstMotorcycle.honk());        // Output: "Beep."
console.log(myFirstMotorcycle.revEngine());   // Output: "VROOM!!!"
console.log(myFirstMotorcycle.numWheels);     // Output: 2

**Part four, create a class for a Garage.**
class Garage {
  constructor(capacity) {
    this.vehicles = [];
    this.capacity = capacity;
  }

  add(vehicle) {
    if (!(vehicle instanceof Vehicle)) {
      return "Only vehicles are allowed in here!";
    }

    if (this.vehicles.length >= this.capacity) {
      return "Sorry, we're full.";
    }

    this.vehicles.push(vehicle);
    return "Vehicle added to the garage.";
  }
}

// Example usage:
let myGarage = new Garage(3);

let myFirstVehicle = new Vehicle("Honda", "Monster Truck", 1999);
console.log(myGarage.add(myFirstVehicle)); // Output: "Vehicle added to the garage."

let mySecondVehicle = new Car("Toyota", "Corolla", 2005);
console.log(myGarage.add(mySecondVehicle)); // Output: "Vehicle added to the garage."

let invalidVehicle = { make: "Invalid", model: "Vehicle", year: 2021 };
console.log(myGarage.add(invalidVehicle)); // Output: "Only vehicles are allowed in here!"

let myThirdVehicle = new Motorcycle("Honda", "Nighthawk", 2000);
console.log(myGarage.add(myThirdVehicle)); // Output: "Sorry, we're full."

