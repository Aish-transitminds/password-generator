# password-generator
password generator
import random
import string

def generate_password(email):
    """Generates a password that satisfies the given conditions."""
    # Define the valid character sets
    letters = string.ascii_letters
    digits = string.digits
    special_characters = "!@#$%&*()-_=+[]{}|;:'\",.<>?/"

    # Combine all character sets except the caret '^'
    all_characters = letters + digits + special_characters

    # Ensure the password length is between 8 and 14
    password_length = random.randint(8, 14)

    while True:
        # Generate a random password of the determined length
        password = ''.join(random.choices(all_characters, k=password_length))

        # Ensure the password doesn't match the email
        if password not in email:
            return password

# Example usage
try:
    email_id = input("Enter your email ID: ")
    password = generate_password(email_id)
    print(f"Generated password: {password}")
except KeyboardInterrupt:
    print("\nOperation interrupted by user.")
