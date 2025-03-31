Projeto DoeSangue

## Diagrama de Classes

```mermaid
classDiagram
    class Donor {
        +int id
        +string name
        +string bloodType
        +string lastDonation
        +List<Donation> donationHistory
    }

    class Donation {
        +string date
        +string type
    }

    class BloodBank {
        +int id
        +string location
        +BloodAvailability bloodAvailability
    }

    class BloodAvailability {
        +int OPositive
        +int ONegative
        +int APositive
        +int ANegative
        +int BPositive
        +int BNegative
        +int ABPositive
        +int ABNegative
    }

    class Notification {
        +int donorId
        +string message
        +string notificationDate
    }

    Donor "1" --> "*" Donation : has
    BloodBank "1" --> "1" BloodAvailability : contains
    Donor "1" --> "*" Notification : receives

