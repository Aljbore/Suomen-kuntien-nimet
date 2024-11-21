#include <iostream>
#include <map>
#include <string>
#include <vector>

int main() {
    // Lista kunnista
    std::vector<std::string> kunnat = {
        "Akaa", "Espoo", "Helsinki", "Vantaa", "Oulu", "Turku", "Tampere",
        "Jyväskylä", "Lahti", "Kuopio", "Porvoo", "Rovaniemi", "Savonlinna"
    };

    // Määritetään map, johon tallennetaan alkukirjainten määrät
    std::map<char, int> kirjaintenLkm;

    // Käydään läpi jokainen kunnan nimi
    for (const auto& kunta : kunnat) {
        if (!kunta.empty()) {
            // Haetaan kunnan nimen ensimmäinen kirjain ja muutetaan se isoksi kirjaimeksi
            char alkukirjain = toupper(kunta[0]);
            // Kasvatetaan vastaavaa kirjainta mapissa
            kirjaintenLkm[alkukirjain]++;
        }
    }

    // Tulostetaan tulokset
    std::cout << "Alkukirjainten lukumäärät kunnannimissä:" << std::endl;
    for (const auto& pari : kirjaintenLkm) {
        std::cout << pari.first << ": " << pari.second << " kuntaa" << std::endl;
    }

    return 0;
}
