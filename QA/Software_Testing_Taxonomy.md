# Software Testing Taxonomy: From Strategy to Execution

In a professional QA ecosystem, these terms represent different levels of 
abstraction. As a Senior QA Architect, I view these as a hierarchical 
dependency chain where the output of one stage becomes the input for the next.

## 1. The Strategic Layer (The Blueprint)
These elements define the "Why" and "How" of the testing effort before any 
actual tests are written.

*   **Test Plan**: A high-level document detailing the strategy, resources, 
    schedule, scope, and risks. It is the "Master Contract" for the project.
*   **Test Template**: A standardized format used to ensure consistency across 
    the team. It defines what fields a test case must have (e.g., Pre-conditions, 
    Steps, Expected Results) so that any engineer can execute any test.

## 2. The Design Layer (The Definition)
This is where requirements are translated into actionable testing assets.

*   **Test Scenario**: A high-level classification of a functionality to be 
    tested. It describes "What" to test without detailing "How." 
    *Example: "Verify the User Login functionality."*
*   **Test Case**: A set of specific inputs, execution steps, and expected 
    results derived from a scenario. It is the smallest unit of test design. 
    *Example: "Enter valid email, enter wrong password, click login -> 
    expect error message."*
*   **Test Suite**: A logical collection of test cases grouped together for a 
    specific purpose. 
    *Example: A "Smoke Suite" for critical paths or a "Regression Suite" for 
    full system stability.*

## 3. The Execution Layer (The Action)
This layer is where the design meets the software build.

*   **Test Cycle**: A specific time-boxed window or version-specific execution 
    event. A cycle often involves running a specific suite against a specific 
    build. 
    *Example: "Sprint 24 Regression Cycle."*
*   **Test Run**: The actual instance of executing a single test case during a 
    cycle. While a test case is a "template" for a test, the run is the 
    "event" of executing it.
*   **Test Results**: The final outcome of a Test Run. This is the evidence 
    (Pass, Fail, Blocked, or Skipped) accompanied by logs or screenshots.

---

## Summary Table: Key Differences

| Term | Primary Purpose | Level of Detail | Key Difference |
| :--- | :--- | :--- | :--- |
| **Scenario** | Coverage | High | Focuses on "What" $\rightarrow$ Case focuses on "How" |
| **Case** | Validation | Low | The blueprint $\rightarrow$ Run is the execution |
| **Suite** | Organization | Medium | A folder/container for multiple Test Cases |
| **Cycle** | Scheduling | High | The time-window $\rightarrow$ Run is the specific action |
| **Run** | Execution | Low | One instance of a Case being executed |

---

## The Systemic Connection (The Workflow)

To visualize how these connect, follow the lifecycle of a single feature:

1.  **Plan**: The **Test Plan** identifies that "User Login" is in scope.
2.  **Template**: The QA lead provides a **Test Template** for consistency.
3.  **Scenario**: The analyst defines a **Test Scenario**: "Verify Login."
4.  **Case**: The engineer writes 5 **Test Cases** (Positive, Negative, Edge) 
    based on that scenario using the template.
5.  **Suite**: These cases are added to the "Authentication **Test Suite**."
6.  **Cycle**: A new build is deployed; the "Regression **Test Cycle**" begins.
7.  **Run**: The engineer performs a **Test Run** for each case in the suite.
8.  **Results**: The **Test Results** are logged, and bugs are filed for any 
    "Fail" outcomes.
