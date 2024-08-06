# Database Design and Build 

Design Questions

1) (3 PTS) What tables should you build?
- `courses` table 
- `learning_outcomes` table
- `instructor` table 
- `course_assignment` table


2) (2 PTS) For each table, what field(s) will you use for primary key? 
- `courses` table -> `mnemonic`
- `learning_outcomes` table -> `learning_outcome_id`
- `instructor` table -> `instructor_id`
- `course_assignment` table -> `course_assignment_id` which is `instructor_id` + `mnemonic`

3) (2 PTS) For each table, what foreign keys will you use?
- `courses` table: `mnemonic` from the `course_assignment` table 
- `learning_outcomes` table: `mnemonic` from the `courses` table
- `instructor` table: `instructor_id` from the `course_assignemnt` table 
- `course_assignment` table: `instructor_id` & `mnemonic`

4) (2 PTS) Learning outcomes, courses, and instructors need a flag to indicate if they are currently active or not. How will your database support this feature? In particular:

- In the `learning_outcomes` table, there will be a column that indicates whether the course is active or not.
- In the `course` table, there will be a column that indicates whether the course is active or not.
- In the `instructors` table, there will be a column that indicates whether the instructor is active or not.  

5) (1 PT) Is there anything to normalize in the database, and if so, how will you normalize it? Recall the desire to eliminate redundancy.

- 1NF: 
    - All tables are atomic in nature
    - All tables have a primary key 
    - no duplications 
- 2NF: 
    - All tables have no partial dependency
    - All non-key attributes are fully dependent on a primary key
- 3NF: 
    - All tables have no transitive partial dependency


6) (1 PT) Are there indexes that you should build? Explain your reasoning.

- Primary & Foreign Key should be indexed to speed up queries. 

7) (2 PTS) Are there constraints to enforce? Explain your answer and strategy. For example, these actions should not be allowed:
- Entering learning objectives for a course not offered by the School of Data Science
- Assigning an invalid instructor to a course
- Inactive Instructors cannot be assigned courses 
- Inactive courses cannot be assigned to instrictors 

8) (5 PTS) Draw and submit a Relational Model for your project. For an example, see Beginning Database Design Solutions page 115 Figure 5-28.

https://lucid.app/lucidchart/597d18c5-708d-453b-8dc7-6595992042b0/edit?viewport_loc=-1735%2C736%2C1917%2C1431%2C0_0&invitationId=inv_42728779-78df-4ccd-bc73-6d0818f30d24


9) (2 PTS) Suppose you were asked if your database could also support the UVA SDS Residential MSDS Program. Explain any issues that might arise, changes to the database structure (schema), and new data that might be needed. Note you won’t actually need to support this use case for the project.

The key concern would be accounting for a phyisical location. This would includes things like timings, buildings, room avaibility, classrom rtpe (i.e. computer lab or lecture hall) and capacity. 