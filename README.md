import random
import string

def generate_password(length):
    if length < 4:
        raise ValueError("Password length should be at least 4")
    chars = string.ascii_letters + string.digits + string.punctuation
    password = [
        random.choice(string.ascii_lowercase),
        random.choice(string.ascii_uppercase),
        random.choice(string.digits),
        random.choice(string.punctuation)
    ]
    password += [random.choice(chars) for _ in range(length - 4)]
    random.shuffle(password)
    return ''.join(password)

if __name__ == "__main__":
    try:
        length = int(input("Enter password length: "))
        print("Generated password:", generate_password(length))
    except Exception as e:
        print("Error:", e)
