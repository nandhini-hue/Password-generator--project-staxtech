import random
import string

def generate_password(length=12):
    # Characters to choose from
    all_chars = string.ascii_letters + string.digits + string.punctuation

    # Ensure password contains at least one character from each category
    password = [
        random.choice(string.ascii_lowercase),
        random.choice(string.ascii_uppercase),
        random.choice(string.digits),
        random.choice(string.punctuation)
    ]

    # Fill the rest of the password length with random characters
    password += random.choices(all_chars, k=length - 4)

    # Shuffle the list to make the password unpredictable
    random.shuffle(password)

    return ''.join(password)

# Example usage
print("Generated Password:", generate_password(12))# Password-generator--project-staxtech
