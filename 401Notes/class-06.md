# Inheritance and Interfaces
- the inheritance is a big part of OOP, it give me the access to another features in any class and use it in my new class.
- the syntax of adding class features from another class ```class derived-class extends base-class  
{  
   //methods and fields  
}  ```
- you you use inheritance, and you want to use any feature from base class, you will use the keyword `super ==> refering to parent class`.
- here is an example using super class called Bicycle and subclass called MountainBike:([source of example](https://www.geeksforgeeks.org/inheritance-in-java/))
```// Java program to illustrate the
// concept of inheritance

// base class
class Bicycle {
	// the Bicycle class has two fields
	public int gear;
	public int speed;

	// the Bicycle class has one constructor
	public Bicycle(int gear, int speed)
	{
		this.gear = gear;
		this.speed = speed;
	}

	// the Bicycle class has three methods
	public void applyBrake(int decrement)
	{
		speed -= decrement;
	}

	public void speedUp(int increment)
	{
		speed += increment;
	}

	// toString() method to print info of Bicycle
	public String toString()
	{
		return ("No of gears are " + gear + "\n"
				+ "speed of bicycle is " + speed);
	}
}

// derived class
class MountainBike extends Bicycle {

	// the MountainBike subclass adds one more field
	public int seatHeight;

	// the MountainBike subclass has one constructor
	public MountainBike(int gear, int speed,
						int startHeight)
	{
		// invoking base-class(Bicycle) constructor
		super(gear, speed);
		seatHeight = startHeight;
	}

	// the MountainBike subclass adds one more method
	public void setHeight(int newValue)
	{
		seatHeight = newValue;
	}

	// overriding toString() method
	// of Bicycle to print more info
	@Override public String toString()
	{
		return (super.toString() + "\nseat height is "
				+ seatHeight);
	}
}

// driver class
public class Test {
	public static void main(String args[])
	{

		MountainBike mb = new MountainBike(3, 100, 25);
		System.out.println(mb.toString());
	}
}
```
```
Output

No of gears are 3
speed of bicycle is 100
seat height is 25

```
- as you can see in the example you can access the the methods and field from subclass and that will create in memory place for those features.
- you can have the same name of method in those two classes, with what we call it overloading.
- when you do an object of subclass, the object of superclass will not created automatically.
- the interface is like a blueprint for class, it's just make the fields and methods without body.
- the syntax of writing an interface is:
 ```
interface interface_name {
    declare constant fields
    declare methods that abstract by default.
}
```
- in interface all methods will be public and final and static.
- when we want to use interface we use the `implement` keyword.
- in general we use the interface for three reasons:
1. to achieve total abstraction.
1. to achieve multiple inheritance.
1. to achieve loose coupling
It is also used .
- the abstract class can have a non final varibale, so we can use them in flexible way.
- abstract class mean that we can not use this class to make object directly from it.
- real example on interface ([source of example](https://www.geeksforgeeks.org/interfaces-in-java/))
```
import java.io.*;
  
interface Vehicle {
      
    // all are the abstract methods.
    void changeGear(int a);
    void speedUp(int a);
    void applyBrakes(int a);
}
  
class Bicycle implements Vehicle{
      
    int speed;
    int gear;
      
     // to change gear
    @Override
    public void changeGear(int newGear){
          
        gear = newGear;
    }
      
    // to increase speed
    @Override
    public void speedUp(int increment){
          
        speed = speed + increment;
    }
      
    // to decrease speed
    @Override
    public void applyBrakes(int decrement){
          
        speed = speed - decrement;
    }
      
    public void printStates() {
         System.out.println("speed: " + speed
              + " gear: " + gear);
    }
}
  
class Bike implements Vehicle {
      
    int speed;
    int gear;
      
    // to change gear
    @Override
    public void changeGear(int newGear){
          
        gear = newGear;
    }
      
    // to increase speed
    @Override
    public void speedUp(int increment){
          
        speed = speed + increment;
    }
      
    // to decrease speed
    @Override
    public void applyBrakes(int decrement){
          
        speed = speed - decrement;
    }
      
    public void printStates() {
         System.out.println("speed: " + speed
             + " gear: " + gear);
    }
      
}
class GFG {
      
    public static void main (String[] args) {
      
        // creating an inatance of Bicycle 
        // doing some operations 
        Bicycle bicycle = new Bicycle();
        bicycle.changeGear(2);
        bicycle.speedUp(3);
        bicycle.applyBrakes(1);
          
        System.out.println("Bicycle present state :");
        bicycle.printStates();
          
        // creating instance of the bike.
        Bike bike = new Bike();
        bike.changeGear(1);
        bike.speedUp(4);
        bike.applyBrakes(3);
          
        System.out.println("Bike present state :");
        bike.printStates();
    }
}
```
```
Output;

Bicycle present state :
speed: 2 gear: 2
Bike present state :
speed: 1 gear: 1
```