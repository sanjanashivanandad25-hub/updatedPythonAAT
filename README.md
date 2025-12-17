# updatedPythonAAT[pythonAAT.py](https://github.com/user-attachments/files/24219639/pythonAAT.py)
print("---------------------------------------------------------SGPA CALCULATOR-------------------------------------------------------")
sub = {
    "Maths": 4,
    "ETC":3,
    "ESC":3,
}
sub_lab={
    "Chemistry": 4,
    "Python":4,
}
def best_two_cie(cie_marks):
    cie_marks.sort(reverse=True)
    return cie_marks[0] + cie_marks[1]

def grade_point(total_marks):
    if total_marks >= 90:
        return 10
    elif total_marks >= 80:
        return 9
    elif total_marks >= 70:
        return 8
    elif total_marks >= 60:
        return 7
    elif total_marks >= 50:
        return 6
    elif total_marks >= 40:
        return 5
    else:
        return 0

total_credit_points = 0
total_credits = 0

for subject, credit in sub.items():
    print(f"\nEnter marks for {subject}")

    cie1 = float(input("CIE 1 (out of 20): "))
    cie2 = float(input("CIE 2 (out of 20): "))
    cie3 = float(input("CIE 3 (out of 20): "))

    cie_total = best_two_cie([cie1, cie2, cie3])

    aat = float(input("AAT/Quiz (out of 10): "))
    see=float(input("SEE marks (out of 100): "))
    reduced_see= see/2
    total_marks = cie_total + aat +reduced_see

    gp = grade_point(total_marks)

    total_credit_points += gp * credit
    total_credits += credit

    print(f"Best 2 CIE total: {cie_total}")
    print(f"Total Marks: {total_marks}")
    print(f"Grade Point: {gp}")
    print("------------------------------------------------------------------------------------------------------------------------------")
for subject,credit in sub_lab.items():
    print(f"\nEnter marks for {subject}")

    cie1 = float(input("CIE 1 (out of 10): "))
    cie2 = float(input("CIE 2 (out of 10): "))
    cie3 = float(input("CIE 3 (out of 10): "))

    cie_total = best_two_cie([cie1, cie2, cie3])

    aat = float(input("AAT / Quiz (out of 5): "))
    lab=float(input("Enter the lab marks(out of 25): "))
    see=float(input("SEE Marks(out of 100): "))
    reduced_see=see/2
    total_marks = cie_total + aat + lab +reduced_see

    gp = grade_point(total_marks)

    total_credit_points += gp * credit
    total_credits += credit

    print(f"Best 2 CIE total: {cie_total}")
    print(f"Total Marks: {total_marks}")
    print(f"Grade Point: {gp}")
    print("------------------------------------------------------------------------------------------------------------------------------")

print("AEC!!")
aec1=input("enter marks for cie1(out of 25): ")
aec2=input("enter marks for cie2(out of 25): ")
aec3=input("enter marks for SEE(out of 50): ")
total_marks=int(aec1)+int(aec2)+int(aec3)
print(total_marks)
aecgp=grade_point(total_marks)
print("Idealab!!")
idealab = input("Enter marks for idealab (out of 50): ")
ilb=int(idealab)*2
ilbgp=grade_point(ilb)
print("idealab grade point:",grade_point(ilb))
total_credit_points+=aecgp+ilbgp
total_credits+=2
sgpa = total_credit_points / 20
print("\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~SGPA RESULT~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
print(f"SGPA = {sgpa:.2f}")


