#include <iostream>
#include <filesystem>

int main() {
    std::filesystem::path sourcePath = "/home/ubuntu/Desktop/workcpp/"; // bu yerda  nusxalamoqchi bo'lgan papkamizni yo'lini ko'rsatamiz
    std::filesystem::path destPath = "/home/ubuntu/Downloads/backup/"; // bu yerda nuslagan papkamizni qayerga joylashtirish yo'lini ko'rsatamiz

    try {
        std::filesystem::copy(sourcePath, destPath, std::filesystem::copy_options::recursive); // Papkani nusxalash jarayoni
        std::cout << "Papka nusxalandi!" << std::endl;
    } catch (const std::filesystem::filesystem_error &e) {
        std::cerr << "Xatolik yuz berdi: " << e.what() << std::endl;
    }

    return 0;
}
