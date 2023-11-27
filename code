//Salla Hela
//20.11.2023
//Tampere
//TAMK
//(c)


#include <iostream>
#include <stdlib.h>;
#include <ctype.h>;

using std::cout;
using std::cin;

int huonemaara (){
    //aliohjelma arpoo koodimaaran
    int maara;
    maara = rand()%41+30; //koodi arpoo huoneiden määrän 30-70
    return maara;
}
int hinta(){
    //aliohjelma arpoo huoneen hinnan
    int arvo;
    arvo = rand()%21+80; //koodi arpoo hinnan 80-100
    return arvo;
}

int main() {
    //määritetään muuuntujat
    int valinta{};

    int hmaara = huonemaara();
    int hotelli [hmaara];
    for(int i = 0; i < hmaara; i++)
        hotelli[i] = 0;
    int hhinta = hinta();
    int yot{};
    int hnro{};
    int varatut{0};


    while (1) {

    std::cout << "Tervetuloa hotellihuoneen varaus palveluun. \n";
    std::cout << "Aloittaaksesi valitse toiminto.\n";
    std::cout << "1.Varaa  2.Lopeta: ";
    std::cin >> valinta;
    alku:
        yo:
        if (valinta==1){
            if (varatut == hmaara){
                std::cout << "Hotellimme on valitettavasti taynna."; //jos huoneita ei ole varattavissa
                break;
            }
            std::cout << "Kuinka monta yota haluat olla?: ";
            std::cin >> yot;

            if (std::cin.fail()){ //jos syötetään muuta kuin numero -> koodi estää ohjelman hajoamisen
                std::cin.clear(); // tyhjentää syötön
                std::cin.ignore(80, '\n'); //ohittaa edellisen syötön
                goto yo;    //vie kohtaan yo
            }

            //tarkistetaan onko hotellihuone vapaana
            tarkistus:

            hnro = rand()%hmaara; //arvotaan huone numero arvotusta huoneen maarasta
            if (hotelli[hnro]==1)
                goto tarkistus; //goto vie kohtaan tarkistus
            else
                hotelli[hnro]=1;


            std::cout << "Oiden maara: " << yot << "\n";
            std::cout << "Varauksen hinta: " << yot * hhinta << "\n";
            std::cout << "Huonenumero: " << hnro << "\n";

            varatut++;
    }
        else if (valinta == 2){
            std::cout << "Kiitos ja tervetuloa uudelleen.";
            break;
        }
        else if (valinta > 2 || valinta < 1||std::cin.fail()) { //jos syötetään muuta kuin 1 tai 2
            std::cin.clear();
            std::cin.ignore(80, '\n');
            std::cout << "Virhe, syota 1 tai 2";
            std::cin >> valinta;
            goto alku; //vie kohtaan alku
        }
