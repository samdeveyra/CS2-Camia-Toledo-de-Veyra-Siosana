# CS2-Camia-Toledo-de-Veyra-Siosana

```
print "Assessment Tracker"
role = "Enter role: student or teacher?"
if role == "student" then
    section = "Enter section: "
    subject = "Enter subject: "
    print "1. View Assessments"
    print "2. View Grade"
    choice = "Enter choice: "
    if choice == 1 then
        print "Subject: ", subject
        print "Assessment name: ", asname
        print "Date of assessment: ", date
        print "Total points: ", pts
        print "Accomplishment status: ", status
        print "Grading status: ", gstatus
    else if choice == 2 then
        print "Your grade: ", grade
    else
        print "Invalid choice"
    end if
else if role == "teacher" then
    section = "Enter section: "
    subject = "Enter subject: "
    print "1. Add Assessment"
    print "2. Remove Assessment"
    print "3. Update Grading Status"
    print "4. Update Accomplishment Status"
    print "5. Update Student Details"
    print "6. Calculate Grade"
    choice = "Enter choice: "
    if choice == 1 then
        asname = "Enter assessment name: "
        date = "Enter date of assessment: "
        pts = "Enter total points: "
        print "Assessment added"
    else if choice == 2 then
        asname = "Enter assessment to remove: "
        print "Assessment removed"
    else if choice == 3 then
        asname = "Enter assessment name: "
        gstatus = "Enter grading status: "
        print "Grading status updated"
    else if choice == 4 then
        asname = "Enter assessment name: "
        status = "Enter accomplishment status: "
        print "Accomplishment status updated"
    else if choice == 5 then
        student = "Enter student name: "
        notes = "Enter missed requirements, absence status, or special exam details: "
        print "Student details updated"
    else if choice == 6 then
        student = "Enter student name: "
        score = "Enter student score: "
        total = "Enter total points: "
        if total > 0 then
            grade = (score / total) * 100
            print "Final grade: ", grade, "%"
        else
            print "Total points must be greater than zero"
        end if
    else
        print "Invalid choice"
    end if
else
    print "Invalid role"
end if
