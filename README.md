> **Romanian version available:** [README.ro.md](README.ro.md)

# Hospital Management System

This project implements an **object-oriented Hospital Management System** designed to simulate and manage core hospital activities, including patient administration, medical staff workflows, and the execution of medical services.

The application is developed in **C++** and uses **CMake** as the build system. Its primary goal is to demonstrate a **clean, structured, and meaningful application of object-oriented programming principles**, together with modern C++ features such as the **Standard Template Library (STL)**, **class templates**, **exception handling**, and **design patterns**.

The system emphasizes:
- clear separation of responsibilities between components,
- safe and maintainable object ownership,
- realistic interactions between entities found in a hospital environment.

---

## General Structure

The project is organized around multiple interacting class hierarchies that model real-world hospital entities. Each hierarchy encapsulates a well-defined responsibility and collaborates with others through composition and polymorphic behavior.

### 1. Person Hierarchy

The **Person hierarchy** models all human actors involved in the hospital workflow.

**Base class:** `Person` *(abstract)*  
Represents a generic individual identified by common attributes and behaviors shared across all persons.

**Derived classes:**
- **`Patient`**  
  Represents a person receiving medical care. Patients maintain medical status information and interact with medical services through evaluations, treatments, and procedures.

- **`HospitalStaff`** *(abstract)*  
  Represents medical personnel employed by the hospital. This class defines shared behavior for all staff members and serves as a polymorphic base for specialized roles.

  **Specialized subclasses:**
  - **`Doctor`**
    - evaluates and diagnoses patients
    - prescribes personalized treatment plans
    - schedules and performs surgical procedures
    - participates in patient discharge decisions
  - **`Nurse`**
    - administers prescribed treatments
    - performs laboratory analyses
    - supports doctors during medical procedures

Polymorphism is used extensively to enable uniform handling of different person types while preserving role-specific behavior.

---

### 2. Service Hierarchy

The **Service hierarchy** models medical activities performed within the hospital.

**Base class:** `Service`  
Defines the common interface for all medical services and enables polymorphic execution and tracking.

**Derived classes:**
- **`Consultation`**  
  Represents a medical consultation between a patient and a doctor.
  - `InitialConsultation` – used for first-time evaluations
  - `FollowUpConsultation` – used for monitoring patient progress
- **`Surgery`**  
  Represents a surgical intervention scheduled and performed by a doctor.
- **`LabTest`**  
  Represents laboratory analyses performed to support medical diagnosis.

Each service type encapsulates its own logic and constraints while exposing a uniform interface to the rest of the system.

---

## Functionalities

The application provides role-based functionality, ensuring that each type of user can only perform actions relevant to their responsibilities.

### Doctor Functionalities
- View all currently admitted patients
- Access and manage the list of scheduled medical appointments
- Evaluate and update patient medical conditions
- Prescribe and adjust personalized treatment plans
- Schedule and perform surgical procedures
- Approve and execute patient discharge
- Calculate performance-based salary bonuses
- Securely log out from the system

### Nurse Functionalities
- View all admitted patients sorted alphabetically
- Administer treatments according to prescribed medical plans
- Perform laboratory tests and record results
- Assist doctors during medical procedures
- Calculate activity-based salary bonuses
- Securely log out from the system

---



## Requirements

### Template Usage
Students must use the template corresponding to their laboratory group:

| Teaching Assistant | Template Link |
|--------------------|---------------|
| Dragoș B           | https://github.com/Ionnier/oop-template |
| Tiberiu M          | https://github.com/MaximTiberiu/oop-template |
| Marius MC          | https://github.com/mcmarius/oop-template |

---

## Build & Compilation Instructions

The project is configured using **CMake**.


### Compilation & Run

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

## Mandatory Requirements

Failure to meet any of the following requirements will result in **automatic disqualification of the project**.

- The program must be written in **C++**
- The program must include an **interactive menu** (used only to demonstrate functionality)
- The program must compile **without errors**
- **No global variables** are allowed
- All data members must be declared as `private` or `protected`
- **GitHub Actions** workflows must pass successfully
- Git commits must be **adequate, consistent, and incremental**
- Avoid meaningless use of language features
- Avoid using language features with the intent of “legally” bypassing other rules, such as:
  - excessive use of `friend` classes
  - excessive use of static members
- Each requirement is graded as follows:
  - **50% for correct implementation**
  - **50% for meaningful and justified usage**

---

## Requirements

- [ ] Definition of at least **2–3 class hierarchies** that interact within the chosen domain  
      (via composition, aggregation, or logical method calls) *(6 points)*

  - At least one class must implement:
    - [ ] initialization constructors  [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] overloaded constructors  [*](https://github.com/Ionnier/poo/tree/main/labs/L02#supra%C3%AEnc%C4%83rcarea-func%C8%9Biilor)
    - [ ] copy constructors  [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] copy assignment operator (`operator=`)  [*](https://github.com/Ionnier/poo/tree/main/labs/L02#supra%C3%AEnc%C4%83rcarea-operatorilor)
    - [ ] destructor  [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] `operator<<` for output (`std::ostream`)  [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L123)
    - [ ] `operator>>` for input (`std::istream`)  [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L128)
    - [ ] one overloaded **member** operator  [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L32)
    - [ ] one overloaded **non-member** operator  [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L39)  
      *(not necessarily declared as `friend`)*

---

### Derived Classes

- [ ] Implementation of domain-specific functionality using **upcasting** and **downcasting**  
      [upcast](https://github.com/Ionnier/poo/tree/main/labs/L04#solu%C8%9Bie-func%C8%9Bii-virtuale-late-binding) / [downcast](https://github.com/Ionnier/poo/tree/main/labs/L04#smarter-downcast-dynamic-cast)

  - This must be demonstrated through **2–3 meaningful methods**
  - Input/output functions and destructors are **excluded**, although they must still be implemented

- [ ] Explicit invocation of the base-class constructor from derived-class constructors   [*](https://github.com/Ionnier/poo/tree/main/labs/L04#comportamentul-constructorului-la-derivare)
- [ ] Properly overridden copy constructors and copy assignment operators (`cc` / `operator=`)   [*](https://github.com/Ionnier/poo/tree/main/labs/L04#comportamentul-constructorului-de-copiere-la-derivare)
- [ ] Use of **virtual destructors** where required  [*](https://github.com/Ionnier/poo/tree/main/labs/L04#solu%C8%9Bie-func%C8%9Bii-virtuale-late-binding)

---

### Additional Constraints

- Only the necessary functionality should be implemented for the remaining classes
- At least **one more complex hierarchy** must exist  
  - base class + **2–3 derived classes**
- A class hierarchy is considered valid even if the base class does not inherit from another hierarchy

- [ ] Extensive and meaningful use of `const`   *(0.25 points)*   [*](https://github.com/Ionnier/poo/tree/main/labs/L04#reminder-const-everywhere)

- [ ] Use of **static members and functions** inside classes  *(0.5 points)*   [*](https://github.com/Ionnier/poo/tree/main/labs/L04#static)
  - [ ] at least **one non-trivial static data member**
  - [ ] at least **one non-trivial static member function**

- [ ] **Exceptions**  *(0.5 points)*  [*](https://github.com/Ionnier/poo/tree/main/labs/L04#exception-handling)

  - custom exception classes derived from `std::exception`
  - demonstration of exception propagation
  - demonstration of upcasting in `catch` blocks
  - used in at least one scenario where classical error handling is difficult

- [ ] Use of at least **one abstract class**  *(0.25 points)*   [*](https://github.com/Ionnier/poo/tree/main/labs/L04#clase-abstracte)

- [ ] **Templates**
  - [ ] creation of one class template  *(1 point)*  [*](https://github.com/Ionnier/poo/tree/main/labs/L08)
  - [ ] at least **two instantiations** of that template  *(0.5 points)*

- [ ] **STL Usage**  *(0.25 points)*  [*](https://github.com/Ionnier/poo/tree/main/labs/L07#stl)

  - [ ] usage of at least **two different STL containers**  
        (e.g. `std::vector`, `std::list`, or similar)
  - [ ] usage of at least **one STL algorithm with a lambda expression**  
        (e.g. `std::sort`, `std::transform`)

- [ ] **Design Patterns**  *(0.75 points)*  [*](https://github.com/Ionnier/poo/tree/main/labs/L08)
  - [ ] implementation of at least **two design patterns**

---

## Notes

- Up to **2 points may be deducted** for issues such as:
  - memory leaks
  - missing virtual destructors where required
  - abuse of certain concepts (e.g. declaring all functions as `virtual`)
  - calling virtual functions inside constructors

- These topics are generally covered by the  
  [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md),  
  but an exhaustive study of the document is **not required**. The code simply needs to be well-structured and responsibly written.

- The `build/` and `install_dir/` directories are included in `.gitignore` because they contain generated files and should not be version-controlled.

