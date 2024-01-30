**Question 1: Circumference Calculation**

```cpp
#include <iostream>
#include <math.h>

using namespace std;

int main() {
    cout << "Enter the radius of the circle: ";
    
    double radius;
    int precision;

    cin >> radius;

    cout << "Enter the precision required for the circumference: ";

    cin >> precision;

    double circumference = 2 * M_PI * radius;

    double multiplier = 1.0;
    for (int i = 0; i < precision; ++i) {
        multiplier *= 10.0;
    }

    double roundedCircumference = static_cast<int>((circumference * multiplier) + 0.5) / multiplier;

    cout << "Circumference with precision " << precision << " is: " << roundedCircumference << endl;
}
```



**Question 2: Data Analysis Program**

```cpp
#include <iostream>
#include <fstream>
#include <iomanip>
#include <map>
#include <vector>

using namespace std;

int main() {
    ifstream inputFile("measurements.txt");

    if (!inputFile.is_open()) {
        cerr << "Error opening the file 'measurements.txt'" << endl;
        return 1;
    }

    map<string, double> totalSumMap;

    double quantity;
    string unit;
    while (inputFile >> quantity >> unit) {
        totalSumMap[unit] += quantity;
    }

    inputFile.close();

    cout << fixed << setprecision(2);
    
    const vector<string> outputOrder = {"meters", "kilograms"};

    for (const auto& unit : outputOrder) {
        if (totalSumMap.find(unit) != totalSumMap.end()) {
            cout << "Total sum of measurements for " << unit << ": " << totalSumMap[unit] << endl;
        }
    }
}

```