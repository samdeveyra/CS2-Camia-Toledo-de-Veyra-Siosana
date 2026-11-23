# CS2-Camia-Toledo-de-Veyra-Siosana

```
PRINT "Assessment Tracker"
assessments_list = []
WHILE true
    section = INPUT "Enter section (or 'exit' to quit)"
    IF section == "exit"
        BREAK
    ENDIF
    role = INPUT "Enter role: student or teacher"
    subject = INPUT "Enter subject"
    IF role == "student"
        PRINT "1. View Assessments"
        PRINT "2. View Grade"
        PRINT "3. Exit"
        choice = INPUT "Enter choice"
        IF choice == "1"
            FOR each item in assessments_list
                IF item.section == section AND item.subject == subject
                    PRINT item.name + " on " + item.date
                    PRINT "Total points: " + item.points
                ENDIF
            ENDFOR
        ELSE IF choice == "2"
            DISPLAY student's saved grade for selected subject
        ELSE IF choice == "3"
            BREAK
        ELSE
            PRINT "Invalid choice"
        ENDIF
    ELSE IF role == "teacher"
        PRINT "1. Add Assessment"
        PRINT "2. Reschedule Assessment"
        PRINT "3. Delete Assessment"
        PRINT "4. View Schedule"
        PRINT "5. Exit"
        choice = INPUT "Enter choice"
        IF choice == "1"
            name = INPUT "Assessment name"
            date = INPUT "Assessment date"
            pts = INPUT "Total points"
            conflict = false
            FOR each item in assessments_list
                IF item.section == section AND item.date == date
                    conflict = true
                ENDIF
            ENDFOR
            WHILE conflict == true
                PRINT "Warning: Date conflict"
                date = INPUT "Enter new date"
                conflict = false
                FOR each item in assessments_list
                    IF item.section == section AND item.date == date
                        conflict = true
                    ENDIF
                ENDFOR
            ENDWHILE
            ADD {section: section, subject: subject, name: name, date: date, points: pts} to assessments_list
            PRINT "Assessment added"
        ELSE IF choice == "2"
            target = INPUT "Assessment name to change"
            new_date = INPUT "Enter new date"
            found = false
            conflict = false
            FOR each item in assessments_list
                IF item.section == section AND item.subject == subject AND item.name == target
                    found = true
                ELSE IF item.section == section AND item.date == new_date
                    conflict = true
                ENDIF
            ENDFOR
            IF found == false
                PRINT "Assessment not found"
            ELSE IF conflict == true
                PRINT "Warning: Date conflict"
            ELSE
                FOR each item in assessments_list
                    IF item.section == section AND item.subject == subject AND item.name == target
                        item.date = new_date
                    ENDIF
                ENDFOR
                PRINT "Rescheduled successfully"
            ENDIF
        ELSE IF choice == "3"
            target = INPUT "Assessment name to delete"
            found = false
            FOR each item in assessments_list
                IF item.section == section AND item.subject == subject AND item.name == target
                    REMOVE item from assessments_list
                    found = true
                    BREAK
                ENDIF
            ENDFOR
            IF found == true
                PRINT "Assessment deleted"
            ELSE
                PRINT "Assessment not found"
            ENDIF
        ELSE IF choice == "4"
            FOR each item in assessments_list
                IF item.section == section
                    PRINT item.subject + ": " + item.name + " on " + item.date
                ENDIF
            ENDFOR
        ELSE IF choice == "5"
            BREAK
        ELSE
            PRINT "Invalid choice"
        ENDIF
    ELSE
        PRINT "Invalid role"
    ENDIF
ENDWHILE
