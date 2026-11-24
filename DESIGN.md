For my capstone Project, I chose the Emergency room triage system. This programe organizes patients based on how serious their current condition is. In an ER, some patients need to be helped right away while others are able to wait. The goal is to make sure the most emergent cases are treated first.


classDiagram
    class Patient {
        -String patientId
        -String name
        -int severityLevel
        -int effectivePriority
        -long arrivalTime
        +getPatientId()
        +getSeverityLevel()
        +getArrivalTime()
    }

    class TriageSystem {
        -PriorityQueue~Patient~ patients
        -ArrayList~Patient~ patientRecords
        -HashMap~String,Patient~
patientLookup
        +addPatient (Patient patient)
        +processNextPatient()
        +viewNextPatient()
        +searchPatient(String id)
        applyAgingRule()
    }
    class Main {
        main(String[] args)
    }
    TriageSystem "1" -> "*"
Patient : manages
    Main -> TriageSystem : uses

Descriptions
Patient: Stores patient information

TriageSystem: Manages patients by organizing priority, and keeping track of waiting time.

Mian: Starts the program


I chose a PriorityQueue because patients need to be treated based on how serious their conditions are. 
I will use three Java data structures:
Priority Queue
Array List
HashMap<String,Patient>


Big O time complexity:
Operation                   Big-O
Add a patient               O(log n)
Process next patient        O(log n)
View next patient           O(1)
Search for patient          O(1)
Waiting times               O(n)