# What is Software Testing? 

## Definition
- A process used to identify correctness/completeness, and quality of developed softwares
- Intended to find errors before the software gets released to the end-users
- "Check if it is defect-free"

## Importance
<p>
Software Testing is important because bugs are dangerous. If we don't test in all possible scenarios, we might confront unexpected bugs that can lead to human/financial loss
</p>

## Testing Principles
1. Testing shows the presence of defects

2. Exhaustive testing is impossible
  - We should come up with optimal amount of testing based on risk assessment
  - The scenario where there is a higher risk of bugs, create more test cases on that

3. Defect Clustering
  - Defects are not uniformly distributed
  - Rather, they are concentrated on small number of modules

4. Early Testing 
  - Testing should start early in the SDLC (Software Developement Life Cycle)

5. Pesticide Paradox
  - Should review/revise test cases regularly to come up with new cases to test the bugs
  - "repeated same test cases --> decrease the chance of discovering new bugs"

6. Testing is context dependent
  - Depends on what we are testing 

7. Absence of errors - fallacy
  - User's want should not be ignored just because we want to remove all errors


## Methodologies
### Waterfall Method (Linear)
<p>
  <img width="772" alt="Screen Shot 2022-11-13 at 1 19 30 PM" src="https://user-images.githubusercontent.com/95491541/201538209-505247a8-0f5c-4027-beab-c75782e82f1c.png">
 </p>
 Advantage: structured, planned, easy to manage (good for small projects)
 <br>
 Disadvantage: Testing happens so late. If bugs are found then, it takes time + cost to "restart"

### V-Model (V-shaped)
<p>
  <img width="822" alt="Screen Shot 2022-11-13 at 1 19 13 PM" src="https://user-images.githubusercontent.com/95491541/201538200-e2bbbf1d-1b5b-4f31-85ba-85668d864934.png">
 </p>
 SDLC --> Verification  STLC --> Validation (improved version of waterfall method)
 <br>
 Advantage: There is a corresponding testing phase for each development stage 
 <br>
 Disadvantage: still not reliable than Agile because testing is executed once the development stage is finished. For agile, testing is carried alongside the development phase. Testers and Developers work together.

 
### Agile Method (Iterative)
<p>
  <img width="772" alt="Screen Shot 2022-11-13 at 1 19 30 PM" src="https://user-images.githubusercontent.com/95491541/201540188-eb038742-18bc-4ac0-b1a9-a0b7c94165b6.jpeg">
  </p>
  How it works: for each phase (adding one functionality to the working version), go through the process (Requirement -> Design -> Build -> Test-> Maintenance)
  <br>
  Advantage: Progressive testing, which allows testers to find bugs easily, flexible to changes, reduce risk

## Unit Testing
- Unit testing is the earliest testing stage in V-model. Practiced after coding phase 
- also called component testing 
- ex) Login System (possible cases: valid ID, invalid ID, empty ID and click Login...)
- meant to be developer's work but testers usually do it

## System Testing 
- System testing is the next stage after integration testing 
- It is about testing the system as a whole, just how a user would use the software
- ex) Login -> check balance -> transfer money -> Logout

## Acceptance Testing 
- done at the client's location by the clients 
- purpose: check whether the software meets their requirements, not to find defects
- 1) alpha testing - done by a small set of employees 
- 2) beta testing - done by a small set of real customers

## Integration Testing 
- tests the data transfer between modules 
- ex) current balance module <-> transfer module (두개가 통신이 잘되는지, 내가 1000불 있었는데 500불 송금하면 500불이 잘 빠져나가는지 확인)
- 1) Big-Bang approach: wait until all modules are developed --> takes too much time + difficult to find bugs 
- 2) Incremental approach: test module when they are available by using stubs and drivers (data transfer 확인하고 싶을때 아직 안만들어놓은 module을 stub라는 임시대체품으로 대신해서 module간의 data transfer를 테스트한다. 여기서도 top-down은 higher level modules먼저 만드는것. bottom-up은 그 반대.


## Smoke/Sanity Testing 
- Possible scenario: when the testers began system testing, they found a defect in earlier module that keep them from moving on to testing the next modules
- Then, the project gets delayed! since the developers must fix the issues before the testing can resume 
- SO! we practice smoke/sanity testing to check the critical functionalities of the system before it is accepted for major testing.


## Regression Testing 
- In the Maintenance Stage, code modifications, function updates, testing enhancements happen.
- Regression testing is used to check if those modications have caused unintended side-effects on the system
- Basically, if the software works as expected even after modifications


## Non-Functional Testing 
- tests performance, usability, endurance, load factor ...
- Performance testing: check system response time. The goal is to reduce the response time 
- Load testing: check the system performance at different loads. Here, the load means the number of people accessing the system 

## Types of Testing 

![IMG_35ED92711CDA-1](https://user-images.githubusercontent.com/95491541/201810713-1053944b-5393-45a3-9068-50a81cbb0a79.jpeg)

## Test Scenario 
- any functionality of a software that can be tested 
- also called Test Condition/Possibility
- Test Prioritization: since exhaustive testing is impossible, we should first test the essential functionalities.

## Test Basis
- To create test cases, we need to base our ideas on something 
- We can rely on AUT (application under testing), our experience, and most importantly Documents
- For each phase of development, look at Document and create test cases based on that 

## How to write a test case 
- Test scenario, test case, pre-conditions, test steps, test data, expected result, actual result, pass/fail 
<img width="1204" alt="Screen Shot 2022-11-15 at 9 33 12 PM" src="https://user-images.githubusercontent.com/95491541/202069703-4e607c66-6e84-46c1-827d-4d9a636f1707.png">

<img width="903" alt="Screen Shot 2022-11-15 at 9 37 30 PM" src="https://user-images.githubusercontent.com/95491541/202070085-f20e34cb-ce8f-49b7-9fe9-69a49578e2a8.png">

## Requirement Traceability Matrix
- if the client changes requirement (e.g. add another feature/another button), we need to change test cases.
- But! it's too hard to find which test cases are affected by that change
- So! label each test case with its Req# (according to each functionality) --> Traceability
  1. when a test case fails, traceability helps us easily find the corresponding functionality
  2. ensures that all functionalities/requirements are tested 

## How to choose test cases/data?
- Since exhaustive testing is impossible, we need to choose which to test 
### Equivalence partitioning 
- black box technique (code is invisible to testers) applicable to all levels of testing 
- Divide the possible values into groups/partitions and pick one value from each partition for testing 
- Then, if one condition in the partition passes, assume that other values in the same partition will also have the same result
![IMG_707FC8D71096-1](https://user-images.githubusercontent.com/95491541/202199899-e0a3de14-2d9e-476d-b452-d28178ef9288.jpeg)

### Boundary Value Analysis 
- test boundary values between partitions
- also called "range checking" 
![IMG_94472E4AAD8E-1](https://user-images.githubusercontent.com/95491541/202199952-51b6bb3f-960e-4708-8115-80375123693b.jpeg)

- Both methods are used together!

### Decision Table Testing 
- deals with combination of inputs which produce different results
- becomes useful as the number of inputs increases
- number of all possible test cases: 2^n. Therefore, by using a decision table, we can choose a good subset to test each condition 

## State Transitioning Diagram (similar to automata)
- helpful where we need to test different system transitions
- 4 main components 
1) states that software may occupy
2) transition from one state to another 
3) events that cause transition
4) action resulted from events

<img width="912" alt="Screen Shot 2022-11-16 at 9 09 25 AM" src="https://user-images.githubusercontent.com/95491541/202203454-cbfdc6b4-0b53-4fa8-a7f7-0f6761c2c9f9.png">

<img width="912" alt="Screen Shot 2022-11-16 at 9 12 16 AM" src="https://user-images.githubusercontent.com/95491541/202203458-5c2bea6d-b9d2-456d-9781-b159b4b30339.png">

## Use Case Testing
- A use case is a series of actions taken by a certain actor that interacts with the system to reach a goal. 
- helps to identify test cases that cover the entire system, on a transaction by transaction basis, from start to finish. It is a description of a particular use of the system by a user.

## Testing Review
- part of "Static Testing" --> software testing technique which is used to check defects in software application without executing the code
- meeting for reviewing software work product (it can be a functional design document)
- helps us detect defects or additional necessary features in the early stage of development 
1. Planning
2. Kick-off
3. Review meeting
4. Rework
5. Follow-up 

## Test Estimation 
- estimating how long it will take to test each functionality
- Work Breakdown Structure Report

## Test Plan 
- a detailed document that describes the test strategy, objectives, schedule, estimation, deliverables, and resources required to perform testing for a software product
- choose what type of testing will be practiced (in scope, out of scope)
- identify risks and set up a mitigation plan 
- It is like a **rule book**, which needs to be followed
<img width="874" alt="Screen Shot 2022-11-17 at 12 46 20 PM" src="https://user-images.githubusercontent.com/95491541/202519848-7c238bab-4aca-456d-a30f-814ac7c87fb9.png">

## Bug Report

<img width="874" alt="Screen Shot 2022-11-17 at 1 03 54 PM" src="https://user-images.githubusercontent.com/95491541/202523852-d06e29bc-4482-48a9-b391-531ad3d0b4c5.png">
- == Bug Report: information needed to be conveyed so that developers can understand what to fix
- Also include Severity and Priority 
i) e.g. a wrong logo --> high priority, low severity
ii) e.g. email-function crash --> low priority, high severity

## Defect Lifecycle

<img width="569" alt="Screen Shot 2022-11-17 at 1 15 47 PM" src="https://user-images.githubusercontent.com/95491541/202525529-6c4f2c1a-0ac4-4123-aa7b-4c2a7cb17cc9.png">
