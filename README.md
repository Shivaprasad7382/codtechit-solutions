def calculate_average(grades):
    return sum(grades) / len(grades) if grades else 0

def letter_grade(average):
    if average >= 90:
        return 'A'
    elif average >= 80:
        return 'B'
    elif average >= 70:
        return 'C'
    elif average >= 60:
        return 'D'
    else:
        return 'F'

def main():
    print("Welcome to the Student Grades Tracker!")
    
    grades = []
    
    while True:
        try:
            grade = input("Enter a grade (or type 'done' to finish): ")
            if grade.lower() == 'done':
                break
            grade = float(grade)
            if 0 <= grade <= 100:
                grades.append(grade)
            else:
                print("Please enter a grade between 0 and 100.")
        except ValueError:
            print("Invalid input! Please enter a numeric value or 'done' to finish.")
    
    if grades:
        average = calculate_average(grades)
        letter = letter_grade(average)
        gpa = average / 20  # Simple GPA calculation, assuming max grade is 100
        
        print("\nGrade Summary:")
        print(f"Grades entered: {grades}")
        print(f"Average grade: {average:.2f}")
        print(f"Letter grade: {letter}")
        print(f"GPA: {gpa:.2f}")
    else:
        print("No grades were entered.")

if __name__ == "__main__":
    main()

