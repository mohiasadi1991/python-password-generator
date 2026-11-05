
import secrets
import string

def generate_password(length=16):
    characters = string.ascii_letters + string.digits + string.punctuation
    return ''.join(secrets.choice(characters) for _ in range(length))

def main():
    print('=== Password Generator ===')
    try:
        length = int(input('Enter password length: '))
        if length < 8:
            print('Please choose at least 8 characters.')
            return
        password = generate_password(length)
        print('\nGenerated password:', password)
    except ValueError:
        print('Please enter a valid number.')

if __name__ == '__main__':
    main()
