# CS2-Camia-Toledo-de-Veyra-Siosana

```
start

print "Assessment Tracker"

input section input role

if role = "Student" then

print assessments
print schedule
print total points
print accomplishment status
print grading status

print "1. View Assessments"
print "2. View Grade"

input choice

if choice = 1 then
    print assessments
else if choice = 2 then
    display personal grade
else
    display "Invalid choice"
end if

else if role = "Teacher" then

print "1. Add/Remove Assessment"
print "2. Update Grading Status"
print "3. Update Accomplishment Status"
print "4. Update Student Details"
print "5. Calculate Grade"

input choice

if choice = 1 then
    add or remove assessment
    input schedule
    input points

else if choice = 2 then
    update grading status

else if choice = 3 then
    update accomplishment status

else if choice = 4 then
    input student
    input special notes

else if choice = 5 then
    calculate grade
    print grade

else
    print "Invalid choice"
end if

else display "Invalid role" end if

stop
```
