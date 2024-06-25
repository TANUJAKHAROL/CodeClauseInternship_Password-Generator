# Secure Password Generator

This is a simple command-line based secure password generator that allows you to create strong passwords with options to include numbers and symbols.

## Features

- Generate passwords of specified length
- Option to include numbers
- Option to include symbols

## Usage

To use the password generator, follow these steps:

1. Run the script.
2. Follow the on-screen prompts to specify the length of the password and whether to include numbers and symbols.

## Code

The main functionality is provided by the `generate_password` function and a simple command-line interface for user interaction.

```python
import random
import string

def generate_password(length, use_numbers=False, use_symbols=False):
    # Define character sets
    letters = string.ascii_letters
    numbers = string.digits if use_numbers else ''
    symbols = string.punctuation if use_symbols else ''

    # Combine character sets based on requirements
    characters = f'{letters}{numbers}{symbols}'

    # Generate password
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def main():
    print("Welcome to the Secure Password Generator!")
    length = int(input("Enter the length of the password: "))
    use_numbers = input("Include numbers? (yes/no): ").lower() == 'yes'
    use_symbols = input("Include symbols? (yes/no): ").lower() == 'yes'

    password = generate_password(length, use_numbers, use_symbols)
    print("Your generated password is:", password)

if __name__ == "__main__":
    main()
