```cpp


#include <iostream>
#include <vector>

int main() {
    std::vector<std::string> skills = {"C++"};
    std::cout << "C++ developer\n";
    for (const auto& s : skills) std::cout << " - " << s << '\n';
}


