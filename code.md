# Assignment3: Abstract Syntax Tree Generation (10% of final grade)
# Due Date: Sunday, November  10, 2024, before 23:59




## Introduction
- This assignment focuses on enhancing the parser developed in Assignment2 by integrating syntax-directed translation to generate an Abstract Syntax Tree (AST) data structure. This AST will be used in later stages of the compiler as an intermediate representation. The parser should retain the features developed in Assignment2.

- This AST will be crucial in later phases of the compiler, where it will be used for semantic checks, code generation, and further processing. This assignment marks the completion of the compiler’s *front end*, creating a structured representation of the source code that is both traversable and usable for subsequent compiler stages.

- The assignment handout includes two example source files that should be used as-is and not altered in any way. Thorough testing is a key grading component; you must provide sufficient test cases covering a wide variety of valid cases, beyond those included in the example source files*.


### Instructions and Hints for Assignment3:
This assignment is not only about coding. A significant part of your success will come from careful planning and understanding the process before diving into the programming.

1. *Understand the Requirements First:*
   - Review the assignment details and instructions. Ensure you fully grasp what is required before starting on the code.
2. *Emphasize Preparation Over Coding:*
   - Similar to Assignment2, where transforming the grammar into LL1 was crucial, here, thoughtful preparation is key. The true challenge lies in structuring and understanding the approach to generating an Abstract Syntax Tree (AST), not just writing code.

3. *Plan Your Approach Before Coding:*
   - Avoid jumping directly into coding without a clear plan. Trying to figure things out as you code can lead to errors that are difficult to fix later. Map out the AST structure, understand how each part fits, and consider how to handle each syntactic structure in the tree before beginning implementation. *Think First, Code Second*, a thorough, step-by-step plan will make coding easier and more efficient.

4. *Integrate Syntax-Directed Translation into Your Parser:*
   - Modify your existing parser to include syntax-directed translation actions.
   - Each translation action will be responsible for building nodes of the AST as the parser recognizes different parts of the source code.
   - *Review Slides for Attribute Grammar:* The lecture slide examples provide insight into how to integrate semantic actions, crucial for building an effective attribute grammar.
5. *Build the Abstract Syntax Tree (AST):*
   - The AST represents the program’s structure in a simplified form, focusing on essential language constructs rather than raw syntax.
   - Your AST should capture all relevant aspects of the source code while abstracting away unneeded elements.
   - *Focus on Intermediate Representation:* Remember that the AST is a cleaner, simplified version of the parse tree. Avoid including syntax elements irrelevant to semantic processing or code generation.


6. *Output the AST:*
   - Save the AST structure to a file, using either a simple text format or a visual format such as graphz DOT. This output file should allow the correctness and structure of the AST to be verified against the parsed program.
   - *Output Clarity:* Ensure the AST output format is readable, well-structured, and aligned with the intended program structure.

7. *Prepare Comprehensive Test Cases:*
   - Develop test cases that cover all syntactical structures your parser can recognize. This ensures the AST generation is robust and handles a wide range of program scenarios.
   - *Test Early and Often:* Use incremental testing as you add syntax-directed actions to your parser, ensuring each part of the AST is constructed as expected.

## Submission Policy
The assignment should contain *only work done by your group this term* or provided by your professor.  Work done in another term (by you or somebody else), or work done by somebody else and not *clearly identified/cited* is considered plagiarism, violating the Academic Integrity Policy.

Every file that you submit must contain (as a comment) at the top *your group number, **group members names , ****group member Seneca emails, and the **date* when you completed the work.

- If the file contains only your work or work provided to you by your professor, add the following message as a comment at the top of the file:

    > I declare this submission is the result of my own work and has not been shared with any other student or 3rd party content provider. This submitted piece of work is entirely of my own creation.
	
- If the file contains work that is not yours (you found it online or somebody provided it to you), *write exactly which parts of the assignment/lab are given to you as help, who gave it to you, or which source you received it from.*  By doing this, you will only lose the mark for the parts you got help for, and the person helping you will be clear of any wrongdoing.


///////////////////////////////////////////////////////////////////////////
// File Name: 
// Group Number: 
// Group Members Names :
// Group Members Seneca Email :
// Date :
// Authenticity Declaration :
// I declare this submission is the result of our group work and has not been
// shared with any other groups/students or 3rd party content provider. This submitted
// piece of work is entirely of my own creation.
//////////////////////////////



## Overview of the Assignment Startup Folder

When you open the startup folder for Assignment3, you will find several important files. Here’s how to make the best use of them:

1. *Read the README File:*
   - The README provides an overview of key resources and instructions, in addition to the following instructions, which detail assignment requirements.

2. *Using the Provided Grammar:*
   - For those who struggled with creating an LL1 grammar in Assignment2, a tested grammar is provided here. This grammar has been validated with tools *AtCC Tool [Website](http://www.atocc.de/cgi-bin/atocc/site.cgi?lang=de&site=main):*, which you can use to verify its correctness.
   - If your current parser and grammar from Assignment2 are functioning correctly, you are welcome to continue using them. However, if you had difficulties, you can use the provided grammar as a starting point for Assignment3.
   - *Flexibility with Grammar Choice:* If your parser from Assignment2 works well with your custom grammar, you can keep using it. However, if you need a reset due to previous challenges, start fresh with the provided grammar to avoid getting stuck on Assignment2 issues.

3. *Examples:*
   - The startup folder includes an *examples* directory with sample source files and corresponding AST output files. These files are demonstration examples to help guide you in structuring your AST output. Note that the source files are written in a different language than the one used in this course’s project. However, these examples still illustrate the format and structure that your output files should resemble, so refer to them as you build your AST output.

## Generating a Visual Representation of the AST
In Assignment3, you are required to output the Abstract Syntax Tree (AST) to a file in a format that is easy to read and inspect, enabling both you and anyone to verify the AST’s structure.

1. *Implement a Tree Traversal Function for AST Output:*
   - Develop a function to traverse your AST (using depth-first search) and print each node in a structured format to a text file. This output should allow easy inspection of the AST’s correctness in relation to the parsed program.
   - *Use Depth-First Traversal:* A depth-first traversal allows you to output nodes in hierarchical order, simplifying the inspection of tree structure.

2. *Choose Your Output Format:*
   - *Text Representation (Required):* The primary requirement is a simple text file that shows the AST’s hierarchy. Start with the root node and list each child node, using indentation to indicate tree depth. This representation helps make the program structure evident.
   - *Graphviz DOT (Optional, Recommended):* If you are familiar with Graphviz, consider outputting your AST as a .dot or .gv file. Tools like Graphviz can interpret .dot files, providing a clear graphical view of your AST.

3. *Additional Visualization Tools:*
   - *DOT Files:* DOT is a graph description language used for defining undirected and directed graphs. DOT files typically have extensions .dot or .gv and can describe the tree structure visually. For more information, refer to the [DOT language documentation](https://graphviz.org/doc/info/lang.html).
   - *Gephi Platform:* Gephi is a powerful, open-source platform for graph visualization and exploration, useful for viewing complex tree structures. You can download Gephi for free at [Gephi Platform](https://gephi.org/).
   - *Consider Graphviz and Gephi for Visualization:* These tools provide a visual representation of your AST, which can be especially useful for debugging more complex tree structures. If you are new to these tools, learning the basics of Graphviz’s DOT language or experimenting with Gephi can enhance your understanding of AST visualization.

4. *Use Example Source and AST Files in Startup Folder:*
   - The startup folder includes an *examples* directory with sample source files and corresponding AST output files. These files are demonstration examples to help guide you in structuring your AST output. Note that the source files are written in a different language than the one used in this course’s project. However, these examples still illustrate the format and structure that your output files should resemble, so refer to them as you build your AST output.

## Deliverables and Group Work

### Document
You must provide a short document that includes the following sections:

- *Assignment Document*: Create an assignment document with the following name format:
  
  group_<number>_assign_<Assignment number>_report.pdf
  
  For example, if group16 creates a report for Assignment20, the report name should be:  
  group_16_assign_20_report.pdf


#### *Section 1. Attribute Grammar:*  
- Begin by creating an *attribute grammar* based on your LL1 grammar. This involves inserting semantic actions into the right-hand sides of your grammar rules, transforming it into an attribute grammar. These semantic actions will later drive the AST generation through syntax-directed translation.

- Provide an attribute grammar that specifies where each *semantic action* is inserted in the grammar’s right-hand sides, along with a list of all semantic actions and a brief description of their effect. See lecture slides for an example.


#### *Section 2.  Design:*
- Offer a brief overview of the solution's structure, including a description of each component's role in the implementation. You need to document the design of your AST generator, describing the structure, flow, and how each component contributes to the AST creation. Detail the process and considerations that went into your design choices.


#### *Section 4. Use of Tools:* 
- Identify all tools/libraries/techniques used in your analysis or implementation. Explain why you chose these specific tools over alternatives.


## Abstract Syntax Tree Implementation

- *Parser augmented with syntax-directed translation:*
	- Implementation of syntax-directed translation in the existing parser for the purpose of generating an AST data structure. The result of the execution of the parser should be the creation of an AST data structure that corresponds to the parse tree as identified by the parsing process. The tree must be an AST, and *not a parse tree*. This tree will become the intermediate representation used by the two following assignments.
	- Whether you are using a recursive descent predictive parser or a table-driven predictive parser, your goal is to implement an *attribute grammar. This involves inserting **semantic actions*—function calls—into the right-hand sides of grammar rules.
	
	- Begin by analyzing the original grammar to identify all the core *semantic concepts* within the language (e.g., expressions, statements, function declarations). This step lays the foundation for understanding the structure of the AST
	
	- *Utilize a Semantic Stack:* Add a *semantic stack* to your parser, which will manage AST nodes. The semantic stack allows you to push new nodes and pop nodes to build the AST as you parse through the program structure. 
	
	- *Define AST Node Data Structures:* Develop data structures to represent AST nodes. These nodes should capture the necessary syntax elements from your language and allow for organized, hierarchical structuring of the AST. For each semantic concept, determine the structure of the *AST subtree* that will represent it. Consider how each concept should be visually and hierarchically organized in the AST. This planning provides a clear conceptual model of the overall tree structure based on the language’s syntax and semantics.
	
	- *Develop the Attribute Grammar:* Now, take your *LL1 grammar* used in the parser and convert it into an *attribute grammar* by adding *semantic actions*. These actions will drive the AST construction by creating nodes and subtrees at specific points in the parsing process. Inject these semantic actions carefully within the right-hand sides of grammar rules where each node or subtree should be created. This approach ensures the parser correctly builds the AST as it processes each part of the input program.
	- *Start with a Small Grammar Subset:* Begin with a simple grammar rule, such as variable declaration (refer to lecture slides for an example), and add the necessary semantic actions. Test your parser to ensure it generates the correct AST for this specific rule.
	- *Expand Gradually:* Once you confirm the AST generation is correct for one rule, move to another, like function headers or class declarations. Each time, test your output to verify the AST structure for the new rule.
	- *Avoid "Big Bang" Integration:* Implementing all grammar rules at once can lead to multiple errors that are difficult to troubleshoot. Incremental development makes it easier to pinpoint and correct issues as they arise.


- *AST Output:*
	- The generated tree should be output to a file in a format that allows easy visualization of the structure of the tree. This can be a simple text representation of the tree structure or a *graphiz* dot representation (see examples in the assignment handout). This file must allow the you or instructor to quickly verify that the generated AST is in fact correct with regards to the parsed program. When parsing a file named, for example, originalfilename, the parser should write into a file named originalfilename.outast a text representation of the abstract syntax tree representing the original program.
	- *Text File Output (Required):* Generate a plain text representation of the AST, organizing nodes in a way that visually resembles a tree structure. This format will help you (and anyone) verify the accuracy of the AST.
	- *Graphviz DOT Language (Optional, Recommended):* Use the *DOT language* to represent the AST in a format compatible with Graphviz. DOT files (with extensions .dot or .gv) can be visualized using tools like Graphviz or online viewers, allowing you to see the AST as a graphical tree. This visual tool can be crucial for verifying the structure of your AST.
	- *Verify AST Output at Each Step:* Each time you add a new rule, check that the AST output matches your expectations. This iterative verification helps ensure your final AST is accurate.
	- *Use the DOT Format for Complex Debugging:* For larger and more complex AST structures, DOT and graphical tools like Graphviz can make it much easier to visualize and debug.

- *Test Cases:*
	- Provide a set of source files that enable to test the AST generation for all syntactical structures and sub-structures involved in the language.
	- *Create a Full Set of Test Cases:* Develop a variety of test cases covering a wide range of language constructs to verify that your parser generates the correct AST for each. These tests should demonstrate the accuracy and completeness of your AST generation across different program structures.

- *Driver:*
	- Include a driver that parses all your test files. For each test file, the corresponding outast files should be generated (in addition to all the files that were generated by the previous assignments).
	- Include a README File with the following name format:  group_<number>_assign_<Assignment number>_README. It is crucial to provide a detailed README file explaining how anyone can recompile your code and generate an executable file (.exe) to run your solution. Even if you include a precompiled .exe file, ensure you provide clear documentation on how someone can execute your code from scratch.
	- Ensure that the script for recompiling your code is compatible with GitHub Codespaces since we will be using it to evaluate your submission. 
	- If you compiled your code locally, ensure that the provided .exe file runs smoothly in the GitHub environment which we will use for testing.




## Instructions for Assignment Submission Requirements and Procedure

- *Professionalism in Code and Documentation*: This assignment is an opportunity to demonstrate your professionalism in presenting your solutions. Provide well-documented code and instructions to help others understand how to execute and use your solution. This is an essential aspect of professional software engineering.


- Each submitted assignment should contain the following four components:
  1. Source Code.
  2. A group of test files.
  3. A brief report in PDF format. [See above](#Document) 
  4. An executable named ASTdriver that extracts the tokens from all your test files. For each test file, the corresponding outast files should be generated.

- The assignment provides test files (.src) and their corresponding output files.

- The source code should be separated into modules, following a comprehensible coding style.
- Ensure that the report is in PDF format, following the naming convention mentioned above.

- *Include the following declaration* in your report file:
  
We, __________ (mention your names), declare that the attached Assignment is our own work in accordance with the Seneca Academic Policy. We have not copied any part of this Assignment, manually or electronically, from any other source, including websites, unless specified as references. We have not distributed our work to other students.

##Specify what each member has done towards the completion of this work:

| *Name* | *Task(s)*       |
|----------|-------------------|
| 1.       |                   |
| 2.       |                   |
| 3.       |                   |
| 4.       |                   |

- The assignment should be submitted through *GitHub* per instructor directions.


### Updating Your Repository with Completed Assignment Work

After successfully completing your assignment and ensuring that all tests pass, follow these steps to update the assignment directory in your repository:

#### Organize Files Correctly  
- All files related to the assignment should be stored in a folder named "Assignment3" or "assign3". Please do not place your files in the main folder of your GitHub repository. 

- Inside the Assignment3 folder, you can create subfolders if necessary (e.g., for logs, test cases, output).

- Ensure that any files generated after running your code are kept organized within the Assignment3 folder to facilitate easy evaluation and to trace outputs effectively.



#### 1. Verify Your Location in the Repository:
- If you are using the *Codespaces* virtual machine, make sure you are in the *root directory* of your repository. This is where your .git folder and other project files are located. 


#### 2. Stage Your Changes:
- Use the following command to stage all your changes for commit:
  
  git add .
  
- This command adds all the modified files in your current directory (and subdirectories) to the staging area, preparing them for a commit.
#### 3. Commit Your Changes:
- Commit your changes with an appropriate message. For instance:
  
  git commit -m "A3 Completed"
  
- This step records your changes in the repository's history. The message "A2 Completed" clearly indicates what this commit represents.

#### 4. Push Your Changes to GitHub:
- Finally, push your changes to your GitHub repository with:
  
  git push origin
  
- This command uploads your recent commit(s) to the remote repository on GitHub.


#### Important Note:
- *Ensuring Successful Update: Executing these steps will commit and push the changes you made during the development of your code while using the virtual machine to your main GitHub repository. It is crucial to regularly **commit and push your changes to avoid losing any work and to keep your remote repository up to date with your local progress*.




#### *Repository Location*:
   - Ensure your code is located in the main branch of your assigned GitHub repository, specifically in the assignment3 folder.
   
#### *Academic Integrity*:
   - *DO NOT* publish your solution in a public repository or share it with others. Doing so is a violation of academic integrity and may be considered cheating.   





## Assignment Rubric

The assignment is worth 10% of your final grade and is marked out of 100 as follows:

---

| *Criteria*                                                                                                                       | *Excellent (90-100%)*                                                                                                                                            | *Very Good (70-89%)*                                                                                                                                      | *Good (50-69%)*                                                                                                                                       | *Unsatisfactory (<50%)*                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| *Analysis (10%)*                                                                                                                 |                              |                                            |                                                  |                                               |
| *Attribute grammar that clearly indicates where each of the semantic actions are inserted in the grammar’s right hand sides, as well as a list of all the semantic actions and a brief description of their respective effect. See lecture slide for an example – document Section 1.(10%)*                                                                                                        | Attribute grammar is comprehensive, with clear, precise insertion points and detailed descriptions of all semantic actions.       | Attribute grammar is mostly complete, with clear insertion points and brief descriptions of most semantic actions.                                            | Attribute grammar covers basic elements, but some insertion points or action descriptions are unclear or missing.                                       | Attribute grammar lacks clarity or is incomplete, with several missing or vague insertion points and action descriptions.                              |
| *Design/Implementation (80%)*                                                                                                    |                                                                                                                                                                      |                                                                                                                                                               |                                                                                                                                                          |                                                                                                                                                         |
| *Description/rationale of the overall structure of the solution and the roles of the individual components used in the applied solution – document Section 2. (10%)*                                                                                               | Structure and components are thoroughly explained with a clear rationale; each component’s role in the solution is well defined.                                     | Most components and their roles are well explained, with minor gaps in clarity or rationale.                                                                  | Some components are adequately described, but rationale is minimal or some roles are unclear.                                                           | Lacks a clear explanation of components or rationale; structure is vague or missing descriptions for several components.                               |
| *Syntax-Directed Translation: Correct implementation of syntax-directed translation implemented as part of a top-down predictive parser following the grammar given in this handout, which is generating and AST (not a parse tree) data structure that correctly represents any valid program given in input. (40%)*                                                                                            | Implementation is fully accurate, adhering closely to the provided grammar; generates a correct AST for all valid inputs.                                            | Implementation is mostly accurate, with minor deviations from the grammar; generates a generally correct AST for valid inputs.                               | Implementation shows basic functionality, but some aspects deviate from the grammar; may generate partially correct AST.                                | Major errors in syntax-directed translation; AST generation is incorrect or inconsistent with the provided grammar.                                    |
| **Output of the AST in an outast file. (10%)**                                                                                                        | AST output file is complete, correct, and well-formatted, making the tree structure clear and easily verifiable.                                                     | AST output file is mostly correct, with minor formatting issues; tree structure is generally clear and verifiable.                                           | AST output file is partially correct but lacks clarity or has significant formatting issues that make verification difficult.                          | AST output file is missing, incorrect, or poorly formatted, making the tree structure unclear or unverifiable.                                         |
| *Test Cases Completeness (20%)*                                                                                                | Test cases are thorough, covering all syntactical structures and edge cases with clear, well-documented examples.                                                    | Test cases cover most structures and some edge cases; documentation is mostly complete and clear.                                                             | Test cases cover only basic structures with minimal documentation and limited edge case coverage.                                                       | Test cases are incomplete or undocumented, lacking coverage of key structures and edge cases.                                                          |
| *Use of Tools (10%)*                                                                                                             |                                                                                                                                                                      |                                                                                                                                                               |                                                                                                                                                          |                                                                                                                                                         |
| *Description of tools/libraries/techniques used in the analysis/implementation. Description of other tools that might have been used. Justification of why the chosen tools were selected – document Section 3 (4%)*                                                                                                      | All tools/libraries/techniques are well-justified, with clear reasoning for each choice; shows strong understanding of alternatives.                                | Tools/libraries/techniques are justified with adequate reasoning, though minor gaps in explanations or alternative considerations may exist.                  | Basic justification is provided, but lacks detail; limited awareness of alternative tools/techniques.                                                  | Justification is missing, minimal, or unclear; lacks awareness of why chosen tools were used or viable alternatives.                                   |
| *Successful/correct use of tools/libraries/techniques used in the analysis/implementation (6%)*                                                                                                     | Chosen tools/libraries/techniques are implemented accurately, contributing effectively to the solution.                                                              | Implementation of tools/libraries/techniques is mostly correct, with minor errors or limitations.                                                            | Basic implementation is achieved, but lacks accuracy or effectiveness in parts; some errors in tool usage.                                             | Tool implementation is incorrect or ineffective, with significant errors or lack of understanding in usage.                                            |




### Solution Checklist
---
#### 1 - Attribute Grammar
- [ ] *Clarity:* The attribute grammar is clearly presented and easy to understand.
- [ ] *Completeness:* All grammar rules have been appropriately injected with semantic actions in their right-hand sides.
- [ ] *Specification Statement:* If there are any changes from the original specifications, they are clearly stated.

#### 2 - Design/Rationale of the Solution Structure
- [ ] *Clarity:* The design and structure of the solution are clearly presented and easy to understand.
- [ ] *Completeness:* All components implemented in the solution are mentioned and explained in the design description.

#### 3 - Tools, Libraries, and Techniques Used
- [ ] *Tool List:* All tools, libraries, and techniques used in the analysis and implementation are mentioned.
- [ ] *Justification:* Justification is provided for the choice of each tool, including descriptions of alternatives if applicable. 

#### 4 - Correct implementation of syntax-directed translation implemented as part of a top-down predictive parser following the grammar given in this handout, which is generating and AST (not a parse tree) data structure that correctly represents any valid program given in input.

- [ ] *4.1* Class declarations are correctly handled.
- [ ] *4.2* Data member declarations are correctly included in the AST.
- [ ] *4.3* Member function declarations are accurately processed.
- [ ] *4.4* Inheritance lists are implemented and included.
- [ ] *4.5* Private/Public member visibility is handled.
- [ ] *4.6* Free function definitions are represented correctly.
- [ ] *4.7* Member function definitions are correctly implemented.
- [ ] *4.8* Local variable declarations are properly included in the AST.
- [ ] *4.9* Integer and float variable declarations are represented accurately.
- [ ] *4.10* Array variable declarations are included with correct structure.
- [ ] *4.11* If statements are implemented with the proper AST structure.
- [ ] *4.12* While statements are correctly represented.
- [ ] *4.13* Read/Write statements are implemented in the AST.
- [ ] *4.14* Return statements are represented correctly.
- [ ] *4.15* Assignment statements are properly structured.
- [ ] *4.16* Complex index structures involving [] and (), and expressions as array indices are handled.
- [ ] *4.17* Complex expressions, including addop, multop, relop, unaryop, idnest, and function calls, are correctly implemented in the AST.


#### 5 - Output OutAST File: AST Representation in Text or DOT Format
- [ ] *5.1 Clarity:* The AST output file is clearly readable, whether in text format or DOT format (rendered correctly by a DOT reader as a graph).
- [ ] *5.2 Correctness:* The output represents an Abstract Syntax Tree (AST), not a parse tree.
- [ ] *5.3 Completeness:* All syntactical constructs are included and represented in the output file.

#### 6 - Test Cases  Completeness of Testing (in addition to provided files)
- [ ] *6.1* Test cases for class declarations.
- [ ] *6.2* Test cases for data member declarations.
- [ ] *6.3* Test cases for member function declarations.
- [ ] *6.4* Test cases for inheritance lists.
- [ ] *6.5* Test cases for private/public members.
- [ ] *6.6* Test cases for free function definitions.
- [ ] *6.7* Test cases for member function definitions.
- [ ] *6.8* Test cases for local variable declarations.
- [ ] *6.9* Test cases for int and float variable declarations.
- [ ] *6.10* Test cases for array variable declarations.
- [ ] *6.11* Test cases for if statements.
- [ ] *6.12* Test cases for while statements.
- [ ] *6.13* Test cases for read/write statements.
- [ ] *6.14* Test cases for return statements.
- [ ] *6.15* Test cases for assignment statements.
- [ ] *6.16* Test cases for complex index structures involving [], (), and expressions as array indices.
- [ ] *6.17* Test cases for complex expressions involving addop, multop, relop, unaryop, idnest, and function calls.

#### 7 - Successful/Correct Use of Tools/Libraries/Techniques in Analysis and Implementation
- [ ] *7.1* The program runs without crashes or exceptions during execution.
- [ ] *7.2* Tools presented in the labs are used appropriately, or suitable comparable tools are used effectively.
---

####  Late submissions will incur a 25% penalty each day.

*:warning:Important:* Please note that a successful submission does not guarantee full credit for this assignment. If the professor is not satisfied with your implementation, your professor may ask you to resubmit. Resubmissions will attract a penalty.