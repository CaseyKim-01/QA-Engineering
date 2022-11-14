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

