# US004 - Open Configuration Menu

## 1. Requirements Engineering

### 1.1. User Story Description

As a user, I want to open a configuration menu to adjust table generation settings.

### 1.2. Customer Specifications and Clarifications 

**From the specifications document:**

> N/A

**From the client clarifications:**

> N/A

### 1.3. Acceptance Criteria

* **AC1:** The application must display a configuration interface when the menu is opened.
* **AC2:** The configuration menu must load the latest saved settings (if available).
* **AC3:** The user must be able to close the configuration menu at any time.

### 1.4. Found Out Dependencies

* SQLite database or file system (if configuration is stored persistently)
* UI framework to support modal or screen rendering

### 1.5 Input and Output Data

**Input Data:**

* Selected data:
    * Select configuration Menu

**Output Data:**

* Configuration UI rendered to screen

### 1.6. System Sequence Diagram (SSD)

![System Sequence Diagram](svg/US004-SSD.svg)

**_Other alternatives might exist._**

### 1.7 Other Relevant Remarks

* The configuration menu can be accessed from the main UI toolbar.
* Settings may include layout options, image scaling, font size, column alignment, etc.
