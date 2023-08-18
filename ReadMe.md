

# Blood Bank Analytics

Vitals -Blood Bank Management System has been designed to help small, medium, and large blood banks and blood centers, efficiently plan and manage mobile collection drives, meet regulatory requirements, and improve transfusion safety and traceability.

## :hammer_and_wrench: Technology Stack

- Angular 12
- .NET core 6
- MySQL 12
- Agile Grid 27
- DevExpress 22.1

## :rocket: Methodology

Agile methodology

### Prerequisites

The Client wanted to develop a comprehensive Blood Bank Management Information System (BBMIS) that
will help them improve their processes and overall efficiency of each of their departments such as Blood
Campaign Management, Donor Management, Blood Ordering, reports, billing, Accounts & Payroll. 

### Installation

1. Clone the repo
   ```bash
   git clone <repo_link>
   ```
2. Install NPM packages
   ```bash
   npm install
   ```
3. Run the server (development mode)
   ```bash
   npm run dev
   ```

## :clipboard: Models

### Dispenser

- `status` (open or closed)
- `flow_volume` (how many liters of beer come out per second)
- `openTime` (when the dispenser was last opened)
- `totalServed` (total volume of beer served)
- `totalRevenue` (total revenue from the dispenser)
- `pricePerLiter` (price per liter of beer)
- `totalUses` (how many times the dispenser has been used)
- `totalOpenTime` (total time the dispenser has been open in seconds)
- `currentVolume` (current volume of beer left in the dispenser)

### DispenserHistory

- `dispenser` (ID of the dispenser)
- `openedAt` (when the dispenser was opened)
- `closedAt` (when the dispenser was closed)
- `served` (volume of beer served during this use)
- `revenue` (revenue generated during this use)

## :hammer_and_wrench: Services

### DispenserService
- `createDispenser`: Creates a new dispenser with the provided data.
- `openDispenser`: Opens a dispenser. If the dispenser is already open or if its current volume is 0, it throws an error.
- `closeDispenser`: Closes a dispenser and calculates the volume of beer served, the revenue generated, and the remaining beer. If the dispenser served more than 3 litres or the remaining volume is less than 1 litre, it closes the dispenser.
- `getDispenser`: Retrieves a dispenser by ID.

### DispenserHistoryService

- `createDispenserHistory`: Creates a new dispenser history record with the provided dispenser data.
- `getReport`: Retrieves a report of dispenser usage and revenue for a given time period.


## :warning: Note

This application assumes that all dispensers start with the same initial volume of beer, and that this initial volume is larger than the `flow_volume * totalOpenTime`. If a dispenser's volume goes below 1 litre, the dispenser will be closed automatically.

![alt text](https://github.com/Ironmandeveloper/BloodBank-Analytics/blob/main/BDS.png?raw=true)
![alt text](https://github.com/Ironmandeveloper/BloodBank-Analytics/blob/main/LAB.png?raw=true)
