The following is essentially what amounts to our coding standards. Some
things are rules, some things are guidelines. Pragmatically, there will
sometimes be reasons to not adhere to these rules and guidelines;
exercise common sense. In the general case however, please do your best
to stick to them.

``` c++
// All header files should have an include guard
#ifndef FILENAME_H
#define FILENAME_H

// Group included headers by origin
#include "../local/support.h"
#include "../local/utility.h"

#include <QObject>
#include <QVector3D>

#include <algorithm>
#include <vector>

// Indentation is 4 spaces
// Line endings are unix

class SuperClass
{
public:
    // Base classes should declare a virtual destructor
    virtual ~SuperClass() {}
}

// Type names use camel case, starting with an upper case letter
class Class : public SuperClass
{
private:
    // Prefer C++11 enum class to plain enum
    enum class SomeEnum
    {
        Yes,
        Maybe,
        No
    };

    // Variable names use camel case, starting with a lower case letter
    // Member variable names always start with an underscore
    // Member variables should be given default values in the header where possible
    // Member variables should be declared separately to member functions
    int _numericalValue = 1;
    char _character = '%';
    SomeClass _someClass;

    // Verbose variable names are preferred to abbreviations
    int _longAndDescriptiveVariable = -1;

    // 32 bit floating point literals should use the f suffix
    float _floatingPoint = 1.0f;

    // Null pointer literals should use C++11 nullptr
    int* _pointer = nullptr;

    // Function names use camel case, starting with a lower case letter
    // Member functions that don't change state should be marked const
    void privateFunction() const;

public:
    // Constructors taking a single parameter must be marked explicit
    explicit Class(int parameter) :
        // Member variables that aren't initialised in the header should be initialised in the initialiser list
        _someClass(42)
    {
        privateFunction();
    }

    // Function names should be camel case, starting with a lower case letter
    // There should be no whitespace between the function name and the parameter list
    // There should be no whitespace after the opening bracket or before the closing bracket in the parameter list
    // Pass parameters by const reference if they are a) not primitive types b) not altered in the function body
    // Pointer or reference characters (i.e. *, &, && etc.) should be aligned with the type, not the identifier
    int publicFunction(const Parameter& parameter)
    {
        // Curly brackets always go on their own line, such that opening and closing braces line up
        if(parameter.boolMemberFunction())
        {
            _numericalValue = 4;
            _character = '@';

            return 123;
        }

        return 0;
    }

    // Setters should start with the word set and finish with the name of the member variable
    void setPointer(int* pointer)
    {
        _pointer = pointer;
    }

    // Getters should have the same name as the thing they're getting
    // Functions that do not change state should be marked const
    int* pointer() const
    {
        return _pointer;
    }

    // Multiple parameters to a function should be separated by a comma followed by a space
    void multiParameterFunction(int a, int b, int c)
    {
        // All operators should be surrounded by spaces
        int y = a + b + c;
        // There should be no whitespace after the opening bracket or before the closing bracket
        int z = (a * b) + c;

        // Singular if statements should not use curly brackets
        if(a == b)
            c = 5;
    }

    void doSomething();

    // With long parameter lists, break the line at a sensible place (~120 columns) and continue
    // the parameters directly below, indented
    void longParameterList(std::vector<int> ints, std::map<int, std::vector<int>> intMap,
        char c, float f, long l);
};

void Class::doSomething()
{
    // Use brace initialisation where possible
    std::vector<int> values = {0, 1, 2, 3};
    int accumulator = 0;

    // Use auto where possible
    // Use for each style loops where possible
    for(auto value : values)
        accumulator += value;
}

#endif // FILENAME_H
```