# DotnetConsoleOOP

# ASKED IN BSC.CSIT MODEL QUESTION
# Create a class to show the constructor, property, indexers and encapsulation behaviour of object oriented programming language ( in C#) - BSc.CSIT Model question, .NET centric computing

This repository contains a simple C# console application that demonstrates object-oriented programming (OOP) concepts. 
The application defines a ' Student ' class with encapsulated private fields, properties for accessing those fields, 
and an indexer for accessing an array element.

## Features

- Encapsulation of private fields using properties.
- Use of an indexer to access array elements.
- Basic demonstration of object-oriented programming principles.
# Source code explanation
using System;
namespace OOPConcept
{

    public class Student {
    //making data field private, this data field can't be accessed by outside class;
    //this data fields can be accessed only using Name and Age property below in the outside class
    private string _name;
    private int _age;
    //creating constructor to initialize private fields
    public Student(string name, int age)
    {
        _name = name;
        _age = age;
    }

    //creating property field that can provide access to priavte data fields outside this class, this provide encapsulation.
    public string Name
    {
        get { return _name; }
        set { _name = value; }
    }
    public int Age
    {
        get { return _age; }
        set { _age = value; }
    }
    //creating an array item to show indexer use
    public int[] array = { 22, 23 };
    public int this[int index]
    {
        get { return array[index]; }
        set { array[index] = value; }
    }
}

public class Program
{
    public static void Main(string[] args)
    {
        //  invoking constructor
        Student student = new Student("Ram", 22);
        //  can't access _name here using student._name here because this is outside class
        //  Console.WriteLine("Name: " + student._name);
        //  using property Name to access private _name field in this outside class
        Console.WriteLine("Name: " + student.Name +"\nAge: "+ student.Age);
        // accessing array member item here where we use indexer
        Console.WriteLine("Value at index 1 of array is : "+ student[1]);
    }
}
}
