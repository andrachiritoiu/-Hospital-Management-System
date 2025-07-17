### EN

----
# Hospital Management System
This project implements an object-oriented system for managing activities in a hospital, including patients, medical staff, and medical services.

### 1. Person Hierarchy

- **`Person`** (abstract base class)  
  - **`Patient`**  
  - **`HospitalStaff`** (abstract)  
    - **`Doctor`**  
      - evaluate patients  
      - prescribe treatments  
      - schedule surgeries  
    - **`Nurse`**  
      - administer treatments  
      - perform lab analyses  

### 2. Service Hierarchy

- **`Service`** (base class)  
  - **`Consultation`**  
    - `InitialConsultation`  
    - `FollowUpConsultation`  
  - **`Surgery`**  
  - **`LabTest`**  

---

## Features

### For **Doctors**  
- List all admitted patients  
- View today's appointments  
- Assess patient condition  
- Prescribe personalized treatments  
- Schedule and perform surgeries  
- Discharge patients  
- Calculate performance bonus  
- Log out  

### For **Nurses**  
- List admitted patients (alphabetical)  
- Administer treatments  
- Run lab tests  
- Calculate activity bonus  
- Log out  

---

## Requirements

- **Language:** C++ (no global variables; private/protected members)  
- **Build:** CMake (project files generated via `cmake`)  
- **Menu:** Interactive console menu demonstrating functionality  
- **OOP:**  
  - At least **2–3 class hierarchies** interacting via composition or method calls  
  - One class with:  
    - initialization constructors  
    - overloaded constructors  
    - copy constructor & `operator=`  
    - destructor  
    - `operator<<` and `operator>>`  
    - one member operator overload  
    - one non‑member operator overload  
  - Virtual destructors and proper base‑class constructor chaining  
  - Upcasts/downcasts showcased in meaningful methods  
- **Templates:**  
  - One class template + two instantiations  
- **STL:**  
  - Use at least two containers (e.g., `std::vector`, `std::list`)  
  - One algorithm with a lambda (e.g., `std::sort`)  
- **Static & Constants:**  
  - One or more static data members/functions  
  - Extensive use of `const` where appropriate  
- **Exceptions:**  
  - Derive from `std::exception`  
  - Demonstrate exception propagation and upcasting in `catch` blocks  
- **Design Patterns:**  
  - Apply at least two patterns (e.g., Factory, Observer)  

---

## Compilation & Run

```bash
# Unix / Linux / macOS
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
cmake --build build

# or with helper script
./scripts/cmake.sh configure
./scripts/cmake.sh build

# Windows (GCC + Ninja)
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug -G Ninja
cmake --build build

````






### RO

----

# Sistem de Management pentru Spital
Acest proiect implementează un sistem orientat pe obiect pentru gestionarea activităților dintr-un spital, inclusiv pacienți, personal medical și servicii medicale. 

# Structura Generală

1. Ierarhia Persoanelor
    
Clasă de bază: Persoana  

Clase derivate:  
-Pacient  
-PersonalSpital (abstractă) 
    Subclase:  
         -Medic: evalueaza pacienți, efectuează operații, prescrie rețete  
         -Asistent: administrează tratamente, face analize  
   
2.Ierarhia Serviciilor

Clasa de bază: Servicii 

Clase derivate:  
-Consultatie   
    Subclase:  
           -ConsultatieInitiala  
           -ConsultatieUrmarire  
   
-Operatie  
-Analiza   

# Functionalitati  
Funcționalități Medic:  
-Vizualizează toți pacienții activi internați în spital  
-Accesează lista programărilor medicale curente  
-Evaluează starea medicală a pacienților  
-Prescrie tratamente personalizate  
-Programează intervenții chirurgicale  
-Efectuează externarea pacienților  
-Calculează bonusul salarial în funcție de performanță  
-Se poate deconecta din contul de utilizator  

Funcționalități Asistent:  
-Vizualizează pacienții activi internați, sortați alfabetic  
-Administrează tratamente conform planului medical  
-Realizează analize medicale  
-Calculează bonusul salarial în funcție de activitatea desfășurată  
-Se poate deconecta din contul de utilizator  


# Cerinte:

### Folosiți template-ul corespunzător grupei voastre!

| Laborant  | Link template                                |
|-----------|----------------------------------------------|
| Dragoș B  | https://github.com/Ionnier/oop-template      |
| Tiberiu M | https://github.com/MaximTiberiu/oop-template |
| Marius MC | https://github.com/mcmarius/oop-template     |

## Instrucțiuni de compilare

Proiectul este configurat cu CMake.

Instrucțiuni pentru terminal:

1. Pasul de configurare
```sh
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
# sau ./scripts/cmake.sh configure
```

Sau pe Windows cu GCC:
```sh
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug -G Ninja
# sau ./scripts/cmake.sh configure -g Ninja
```

La acest pas putem cere să generăm fișiere de proiect pentru diverse medii de lucru.

## Cerințe obligatorii

Nerespectarea duce la nepunctarea proiectului

  - programul va fi scris în C++
  - programul va avea un meniu interactiv (doar pentru ilustrarea funcționalității)
  - programul nu are erori de compilare
  - fară variabile globale
  - datele membre private(sau protected)
  - GitHub Actions trecute
  - commit-uri pe Git adecvate si punctuale
  - folosirea a funcționalităților limbajului fără sens
  - folosirea a funcționlităților limbajului cu scopul de a încălca "legal" o altă regulă
      - folosirea excesivă a claselor friend
      - folosirea excesviă a elementelor statice
  - fiecare cerinta va fi punctate 1/2 pe implementare + 1/2 pe faptul ca a fost implementata cu sens

## Cerințe
- [ ] definirea a minim **2-3 ieararhii de clase** care sa interactioneze in cadrul temei alese (fie prin compunere, agregare sau doar sa apeleze metodele celeilalte intr-un mod logic) (6p)
  - minim o clasa cu:
    - [ ] constructori de inițializare [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] constructor supraîncărcat [*](https://github.com/Ionnier/poo/tree/main/labs/L02#supra%C3%AEnc%C4%83rcarea-func%C8%9Biilor)
    - [ ] constructori de copiere [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] `operator=` de copiere [*](https://github.com/Ionnier/poo/tree/main/labs/L02#supra%C3%AEnc%C4%83rcarea-operatorilor)
    - [ ] destructor [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] `operator<<` pentru afișare (std::ostream) [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L123)
    - [ ] `operator>>` pentru citire (std::istream) [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L128)
    - [ ] alt operator supraîncărcat ca funcție membră [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L32)
    - [ ] alt operator supraîncărcat ca funcție non-membră [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L39) - nu neaparat ca friend
  - in derivate
      - [ ] implementarea funcționalităților alese prin [upcast](https://github.com/Ionnier/poo/tree/main/labs/L04#solu%C8%9Bie-func%C8%9Bii-virtuale-late-binding) și [downcast](https://github.com/Ionnier/poo/tree/main/labs/L04#smarter-downcast-dynamic-cast)
        - aceasta va fi făcută prin **2-3** metode specifice temei alese
        - funcțiile pentru citire / afișare sau destructorul nu sunt incluse deși o să trebuiască să le implementați 
      - [ ] apelarea constructorului din clasa de bază din [constructori din derivate](https://github.com/Ionnier/poo/tree/main/labs/L04#comportamentul-constructorului-la-derivare)
      - [ ] suprascris [cc](https://github.com/Ionnier/poo/tree/main/labs/L04#comportamentul-constructorului-de-copiere-la-derivare)/op= pentru copieri/atribuiri corecte
      - [ ] destructor [virtual](https://github.com/Ionnier/poo/tree/main/labs/L04#solu%C8%9Bie-func%C8%9Bii-virtuale-late-binding)
  - pentru celelalte clase se va definii doar ce e nevoie
  - minim o ierarhie mai dezvoltata (cu 2-3 clase dintr-o clasa de baza)
  - ierarhie de clasa se considera si daca exista doar o clasa de bază însă care nu moștenește dintr-o clasă din altă ierarhie
- [ ] cât mai multe `const` [(0.25p)](https://github.com/Ionnier/poo/tree/main/labs/L04#reminder-const-everywhere)
- [ ] funcții și atribute `static` (în clase) [0.5p](https://github.com/Ionnier/poo/tree/main/labs/L04#static)
  - [ ] 1+ atribute statice non-triviale 
  - [ ] 1+ funcții statice non-triviale
- [ ] excepții [0.5p](https://github.com/Ionnier/poo/tree/main/labs/L04#exception-handling)
  - porniți de la `std::exception`
  - ilustrați propagarea excepțiilor
  - ilustrati upcasting-ul în blocurile catch
  - minim folosit într-un loc în care tratarea erorilor în modurile clasice este mai dificilă
- [ ] folosirea unei clase abstracte [(0.25p)](https://github.com/Ionnier/poo/tree/main/labs/L04#clase-abstracte)
 - [ ] clase template
   - [ ] crearea unei clase template [(1p)](https://github.com/Ionnier/poo/tree/main/labs/L08)
   - [ ] 2 instanțieri ale acestei clase (0.5p)
 - STL [(0.25p)](https://github.com/Ionnier/poo/tree/main/labs/L07#stl)
   - [ ] utilizarea a două structuri (containere) diferite (vector, list sau orice alt container care e mai mult sau mai putin un array)
   - [ ] utilizarea a unui algoritm cu funcție lambda (de exemplu, sort, transform)
 - Design Patterns [(0.75p)](https://github.com/Ionnier/poo/tree/main/labs/L08)
   - [ ] utilizarea a două șabloane de proiectare

### Observații

* Pot exista depunctări până la 2p pentru diferite aspecte precum:
  - memory leak-uri
  - nefolosirea destructorului virtual la nevoie
  - abuzarea de diferite concepte (toate funcțiile declarate virtual)
  - apelarea de funcții virtual în constructori

* În general, acestea sunt prezente în [CppCoreGuideline](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md), dar nu e nevoie să parcurgeți documentul, doar să scrieți codul suficient de organizat

* folderele `build/` și `install_dir/` sunt adăugate în fișierul `.gitignore` deoarece
conțin fișiere generate și nu ne ajută să le versionăm.
