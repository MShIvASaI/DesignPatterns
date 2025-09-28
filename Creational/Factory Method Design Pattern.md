# Factory Method Design Pattern

The Factory Method Design Pattern in C++ is a creational pattern that delegates the responsibility of creating objects to subclasses, allowing flexibility and reducing coupling between the client code and the concrete classes that are instantiated.[^1][^2][^5]

### Factory Method Pattern Example in C++

Here is a classic C++ example using a shape factory:

```cpp
#include <iostream>
#include <string>
using namespace std;

class Shape {
public:
    virtual void draw() = 0;
    virtual ~Shape() {}
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing Circle" << endl;
    }
};

class Square : public Shape {
public:
    void draw() override {
        cout << "Drawing Square" << endl;
    }
};

// Factory method in creator class
class ShapeFactory {
public:
    static Shape* createShape(const string& type) {
        if (type == "Circle") return new Circle();
        else if (type == "Square") return new Square();
        else return nullptr;
    }
};

int main() {
    Shape* shape1 = ShapeFactory::createShape("Circle");
    Shape* shape2 = ShapeFactory::createShape("Square");

    shape1->draw();  // Drawing Circle
    shape2->draw();  // Drawing Square

    delete shape1;
    delete shape2;
    return 0;
}
```

This approach delegates object creation to a static factory method, which selects and instantiates concrete product classes (e.g., Circle and Square) depending on input parameters.[^2][^5][^1]

### Components of Factory Method

- **Product**: Abstract base class or interface (e.g., Shape).[^1]
- **Concrete Product**: Specific subclasses created by the factory (e.g., Circle, Square).[^1]
- **Creator**: Abstract class that declares the factory method (not strictly necessary in simple C++ implementations).[^1]
- **Concrete Creator**: Implements the factory method and determines which product gets created (e.g., ShapeFactory).[^5][^1]


### Why Use Factory Method?

- Simplifies creation logic in client code.
- Hides details about concrete classes.
- Supports extension for new object types without changing existing client code.
- Promotes loose coupling and code scalability.[^7][^5][^1]

This pattern is highly used where the exact type of object to create depends on runtime conditions or configuration, such as game character creation, shape generators, or different handlers in software systems.[^5]
<span style="display:none">[^3][^4][^6][^8][^9]</span>

<div align="center">⁂</div>

[^1]: https://www.geeksforgeeks.org/system-design/factory-method-pattern-c-design-patterns/

[^2]: https://refactoring.guru/design-patterns/factory-method/cpp/example

[^3]: https://www.youtube.com/watch?v=usmdZniV_Yw

[^4]: https://sourcemaking.com/design_patterns/factory_method/cpp/1

[^5]: https://www.linkedin.com/pulse/design-pattern-factory-pratik-parvati

[^6]: https://stackoverflow.com/questions/5120768/how-to-implement-the-factory-method-pattern-in-c-correctly

[^7]: https://refactoring.guru/design-patterns/factory-method

[^8]: https://www.youtube.com/watch?v=vAmDQKeC99g

[^9]: https://en.wikipedia.org/wiki/Factory_method_pattern

