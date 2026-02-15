# Election-Management-System-SDA-Case-Study-

## 📌 Project Overview
This project presents a comprehensive Software Design and Architecture (SDA) solution for the Ootumlia Elections Commission. The system is designed to manage complex municipal elections for various elected bodies (school boards, city councils, etc.) while adhering to strict legal and privacy constraints.

### Key Requirements Addressed: 
- Centralized Data Management: Recording names and addresses for all candidates, incumbents, and voters.
- Incumbency Tracking: Facilitating reporting for media outlets regarding seat-holders' performance.
- Voter Anonymity: A hard constraint ensuring no record links a specific voter to their candidate choice.

## 🏗️ Architectural Design

### 1. Functional Analysis (Use Case Diagram) 

The design utilizes a system boundary to separate administrative configuration from day-of-election operations.
- Election Official: Acts as the primary administrator for voter lists and structural setup.
- Poll Worker: Handles station-specific data entry to maintain a separation of concerns.
- Voter Portal: Allows for eligibility verification and poll location without accessing sensitive tally data.

### 2. Structural Design (Class Diagram) 
The class diagram implements several advanced Object-Oriented principles to solve the commission's challenges:

-Inheritance (Generalization): An abstract Person base class centralizes the storage of name and address attributes for all actors.
-Composition: Used between ElectedBody and Seat to reflect the immutable hierarchy of municipal positions.
-Association Class (VoteTally): To enforce Programmatic Anonymity, vote counts are stored as an intersection between a Candidate and a Poll. This ensures that while totals are tracked, no logical path exists to link a Voter record to a specific ballot.

### 3. Design Patterns and Decisions 

-Separation of Concerns: Distinct classes for ElectionOfficial and PollWorker ensure that administrative skillsets do not overlap with field data entry.
- Scalability: The composition of seats within elected bodies allows the system to scale from small school boards to large city councils without structural changes.
- Data Integrity: Using a 1:1 association between Seat and Incumbent provides the Newspaper Reporter with direct, accurate reporting data.

  
