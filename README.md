# Random-wheel
Napravljeno za 15 minuta, prijatelj me izazvao. Testirao sam mogućnost čekanja u C++-u.
#include <iostream>
#include <thread>
#include <chrono>
#include <cstdlib>
#include <ctime>
#include <vector>
#include <string>

void waitForSeconds(int seconds) {
    std::this_thread::sleep_for(std::chrono::seconds(seconds));
}
int main() {
    int n;
    std::cout << "RANDOM WHEEL, input amount of options: ";
    std::cin >> n;
    std::vector<std::string> options(n);
    std::cout << "Enter " << n << " names:\n";
    std::cin.ignore();
    for (int i = 0; i < n; ++i) {
        std::getline(std::cin, options[i]);
    }
    std::cout << "Selecting random, wait for 3 seconds...\n";
    waitForSeconds(3);
    std::srand(std::time(0));
    int g = std::rand() % n;
    std::cout << "The selected option is: " << options[g] << std::endl;
    return 0;
}
