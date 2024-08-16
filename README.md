import re

def password_strength(password):

    length_criteria = 1
    uppercase_criteria = 1
    lowercase_criteria = 1
    digit_criteria = 1
    special_char_criteria = 1
    length_threshold = 8

    score = 0


    if len(password) >= length_threshold:
        score += length_criteria
    else:
        print(f"Password too short! Must be at least {length_threshold} characters long.")


    if re.search(r'[A-Z]', password):
        score += uppercase_criteria
    else:
        print("Password should include at least one uppercase letter.")


    if re.search(r'[a-z]', password):
        score += lowercase_criteria
    else:
        print("Password should include at least one lowercase letter.")


    if re.search(r'[0-9]', password):
        score += digit_criteria
    else:
        print("Password should include at least one digit.")


    if re.search(r'[@$!%*?&]', password):
      score += special_char_criteria
    else:
        print("Password should include at least one special character (@, $, !, %, *, ?, &).")


    if score == 5:
        return "Password is very strong."
    elif 4 <= score < 5:
        return "Password is strong."
    elif 3 <= score < 4:
        return "Password is moderate."
    else:
        return "Password is weak. Consider adding more characters, uppercase letters, numbers, or special characters."


password = input("Enter a password to assess its strength: ")
feedback = password_strength(password)
print(feedback)rd
