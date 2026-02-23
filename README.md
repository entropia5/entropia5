```cpp



#include <iostream>
#include <vector>
#include <string>
#include <memory>
#include <map>


namespace Profile {

    enum class DevLevel { Junior, Middle, Senior, Architect };

    struct Hardware {
        std::string workstation = "Mac (Unix)";
        std::string test_bench = "RPi-Server (ARM64), Linux";
        std::string connectivity = "SSH / Cross-compilation";
    };

    class GamedevDeveloper {
    private:
        std::string name = "NULLABLE";
        float experience_years = 1.0f;
        DevLevel status = DevLevel::Junior;

    public:
        Hardware env;
        
        
        struct Stack {
            std::vector<std::string> languages = {"C++17/20"};
            std::vector<std::string> engines = {"Unreal Engine", "SDL2/SFML (Learning)"};
            std::vector<std::string> tools = {"CMake", "Git", "Clang/LLVM", "GDB"};
            std::vector<std::string> math = {"Linear Algebra", "Vector Math (Learning)"};
        } stack;

        
        std::map<std::string, bool> qualities = {
            {"Genius", false},
            {"Billionaire", false},
            {"Playboy", false},
            {"Philanthropist", false},
            {"ManualMemoryManager", true},
            {"ArchLinuxSurvivor", true}
        };

        void displayPortfolio() const {
            std::cout << "==========================================="
            << std::endl;
            std::cout << "           [C++ DEVELOPER]                 "
            << std::endl;
            std::cout << "==========================================="
            << std::endl;
            std::cout << "> Exp: " << experience_years << " year(s) of pointer debugging." << std::endl;
            std::cout << "> OS: " << env.workstation << " -> " << env.test_bench << std::endl;
            
            std::cout << "\n[CURRENT_SKILLS]:" << std::endl;
            for (const auto& lang : stack.languages) std::cout << " - " << lang << std::endl;

           
        }

        bool isReadyForJob() const {
         
            return (experience_years >= 1.0f && qualities.at("ManualMemoryManager"));
        }
    };
}

int main() {
    
    auto mySelf = std::make_unique<Profile::GamedevDeveloper>();

    if (mySelf->isReadyForJob())
      {
        mySelf->displayPortfolio();
      }

    return 0;
}



