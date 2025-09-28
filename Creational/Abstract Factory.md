### Abstract Factory Pattern Example in C++

```cpp
#include <iostream>
using namespace std;

// Abstract Product
class Pizza {
public:
    virtual void bake() = 0;
    virtual void cut() = 0;
    virtual void box() = 0;
    virtual ~Pizza() {}
};

// Concrete Products
class NewYorkCheesePizza : public Pizza {
public:
    void bake() override { cout << "Baking New York-style cheese pizza.\n"; }
    void cut() override { cout << "Cutting New York-style cheese pizza.\n"; }
    void box() override { cout << "Boxing New York-style cheese pizza.\n"; }
};

class ChicagoCheesePizza : public Pizza {
public:
    void bake() override { cout << "Baking Chicago-style cheese pizza.\n"; }
    void cut() override { cout << "Cutting Chicago-style cheese pizza.\n"; }
    void box() override { cout << "Boxing Chicago-style cheese pizza.\n"; }
};

// Abstract Factory
class PizzaFactory {
public:
    virtual Pizza* createCheesePizza() = 0;
    virtual ~PizzaFactory() {}
};

// Concrete Factories
class NewYorkPizzaFactory : public PizzaFactory {
public:
    Pizza* createCheesePizza() override { return new NewYorkCheesePizza(); }
};

class ChicagoPizzaFactory : public PizzaFactory {
public:
    Pizza* createCheesePizza() override { return new ChicagoCheesePizza(); }
};

int main() {
    PizzaFactory* nyFactory = new NewYorkPizzaFactory();
    PizzaFactory* chicagoFactory = new ChicagoPizzaFactory();

    Pizza* nyPizza = nyFactory->createCheesePizza();
    Pizza* chicagoPizza = chicagoFactory->createCheesePizza();

    nyPizza->bake(); nyPizza->cut(); nyPizza->box();
    chicagoPizza->bake(); chicagoPizza->cut(); chicagoPizza->box();

    delete nyPizza; delete chicagoPizza;
    delete nyFactory; delete chicagoFactory;
    return 0;
}
```

This code uses an abstract factory to create families of related pizza objects by style, keeping client code decoupled from concrete pizza classes.[^2][^1]

### Interview Questions and Variations

- What is the Abstract Factory pattern and where is it useful?[^2][^1]
- How is Abstract Factory different from Factory Method?[^5][^2]
- Can you design an Abstract Factory system for GUI widgets or vehicle parts?
- What are the pros and cons of Abstract Factory?[^1]
- How do you extend an Abstract Factory to support new families without breaking existing code?
- Discuss a real-world scenario where Abstract Factory offers improved scalability and maintainability.
- What is the impact of Abstract Factory on testability, code complexity, and maintenance?[^4][^1]
- Illustrate with UML or code the key participants: abstract factory, concrete factory, abstract product, concrete product.

These questions target implementation skills, pattern knowledge, extensibility, and real-world pattern applicability, typical for C++ design interviews.[^5][^4][^1]
<span style="display:none">[^10][^11][^12][^13][^14][^7][^8][^9]</span>

<div align="center">⁂</div>

[^1]: https://www.geeksforgeeks.org/system-design/abstract-factory-pattern-c-design-patterns/

[^2]: https://refactoring.guru/design-patterns/abstract-factory/cpp/example

[^3]: https://sourcemaking.com/design_patterns/abstract_factory/cpp/2

[^4]: https://dev.to/rk042/master-abstract-factory-design-pattern-for-programming-interviews-with-5-easy-steps-6gi

[^5]: https://in.indeed.com/career-advice/interviewing/design-pattern-interview-questions

[^6]: https://www.interviewbit.com/design-patterns-interview-questions/

[^7]: https://sourcemaking.com/design_patterns/abstract_factory/cpp/before-after

[^8]: https://www.youtube.com/watch?v=17i8a-pUtx8

[^9]: https://www.geeksforgeeks.org/system-design/abstract-factory-pattern/

[^10]: https://softwarepatterns.com/cpp/abstract-factory-software-pattern-cpp-example

[^11]: https://www.bogotobogo.com/DesignPatterns/abstractfactorymethod.php

[^12]: https://www.youtube.com/watch?v=hJgubQLTjZU

[^13]: https://refactoring.guru/design-patterns/abstract-factory

[^14]: http://clinuxcode.blogspot.com/2017/08/factory-method-design-pattern-in-c-and.html

