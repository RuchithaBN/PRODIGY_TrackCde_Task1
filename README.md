# PRODIGY_TrackCde_Task1
def caesar_cipher_encrypt(text, shift):
    encrypted_text = []
    for char in text:
        if char.isalpha():
            shift_amount = shift % 26
            base = ord('A') if char.isupper() else ord('a')
            new_char = chr((ord(char) - base + shift_amount) % 26 + base)
            encrypted_text.append(new_char)
        else:
            encrypted_text.append(char)
    return ''.join(encrypted_text)

def caesar_cipher_decrypt(text, shift):
    return caesar_cipher_encrypt(text, -shift)

def main():
    print("Caesar Cipher Program")

    message = input("Enter the message: ")
    shift = int(input("Enter the shift value: "))

    encrypted_message = caesar_cipher_encrypt(message, shift)
    print("Encrypted message:", encrypted_message)

    decrypted_message = caesar_cipher_decrypt(encrypted_message, shift)
    print("Decrypted message:", decrypted_message)

if __name__ == "__main__":
    main()
