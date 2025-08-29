# AnemoVisionHunt2025

if you cannot open exe files (do not have a windows machine), you can use these instructions to run the LyreTransmuter

Step 1: copy this code:
```C++
#include <iostream>
#include <string>
#include <unordered_map>
#include <vector>
#include <cctype>
const std::string ALPHABET = "ABCDEFGHJMNQRSTUVWXZY"; const int BASE = ALPHABET.size(); const int SYMBOL_SIZE = 2;
std::unordered_map<char, int> buildReverseMap() { std::unordered_map<char, int> map; for (int i = 0; i < BASE; ++i) map[ALPHABET[i]] = i; return map; }
char decodeSymbol(const std::string& sym, const std::unordered_map<char, int>& rev) { if (sym.size() != 2 || rev.find(sym[0]) == rev.end() || rev.find(sym[1]) == rev.end()) return '?'; int value = rev.at(sym[0]) * BASE + rev.at(sym[1]); if (value < 10) return '0' + value; else if (value < 36) return 'a' + (value - 10); return '?'; }
std::string decode(const std::string& encoded) { std::unordered_map<char, int> rev = buildReverseMap(); std::string result; if (encoded.length() % 2 != 0) return "Invalid length"; for (size_t i = 0; i < encoded.length(); i += 2) { std::string sym = encoded.substr(i, 2); result += decodeSymbol(sym, rev); }
return result; }
void printHeader() { std::cout << "~\u266A~ Welcome, Traveler ~\u266A~\nYou\'ve arrived at the \033[1mLyre Transmuter\033[0m \u2014 a mystical tool to reshape your melodies into sacred symbols.\n\n";}
int main() { printHeader();
std::cout << "Unravel a Song\n"; std::string input; std::cout << "\n\u266A Reveal the Sacred Notes: "; std::getline(std::cin, input); std::string decoded = decode(input); std::cout << "\u266A Decoded Verse: " << decoded << "\n"; std::cout << "\nPress Enter to return to Teyvat..."; std::cin.get(); return 0; }
```

step 2: go to an online C++ runner like: https://www.programiz.com/cpp-programming/online-compiler/

step 3: paste in the copied code there and run.


