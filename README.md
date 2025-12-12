import random
import string
print("----- Random Password Generator -----")
# Step 1: User enters desired password length
length = int(input("Enter password length: "))
# Step 2: Options for character types
use_upper = input("Include uppercase letters? (y/n): ").lower() == 'y'
use_lower = input("Include lowercase letters? (y/n): ").lower() == 'y'
use_digits = input("Include digits? (y/n): ").lower() == 'y'
use_symbols = input("Include special characters? (y/n): ").lower() == 'y'
# Step 3: Create character pool based on user choices
characters = ""
if use_upper:
    characters += string.ascii_uppercase     # A–Z
if use_lower:
    characters += string.ascii_lowercase     # a–z
if use_digits:
    characters += string.digits              # 0–9
if use_symbols:
    characters += string.punctuation         # special characters
# Step 4: If user selected nothing
if characters == "":
    print("Error! No character type selected. Using all types by default.")
    characters = string.ascii_letters + string.digits + string.punctuation
# Step 5: Generate password
password = ''.join(random.choice(characters) for _ in range(length))
# Step 6: Display result
print("\nGenerated Strong Password:", password)
