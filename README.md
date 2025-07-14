# Codsoft-task3
import random
import string

print("=== Simple Password Generator ===")

length = int(input("Enter desired password length: "))

use_uppercase = input("Include uppercase letters? (y/n): ").lower() == 'y'
use_lowercase = input("Include lowercase letters? (y/n): ").lower() == 'y'
use_digits = input("Include numbers? (y/n): ").lower() == 'y'
use_symbols = input("Include symbols? (y/n): ").lower() == 'y'

characters = ""

if use_uppercase:
    characters += string.ascii_uppercase
if use_lowercase:
    characters += string.ascii_lowercase
if use_digits:
    characters += string.digits
if use_symbols:
    characters += string.punctuation

if not characters:
    print("Error: No character types selected.")
else:
    password = ''.join(random.choice(characters) for _ in range(length))
    print("\nGenerated password:", password)
