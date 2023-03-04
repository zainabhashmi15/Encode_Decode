# Encode_Decode


def encode_string(s):
    """
    Encodes a string by shifting each letter in the alphabet by one position.
    For example, 'abc' becomes 'bcd', 'xyz' becomes 'yza', etc.
    Non-alphabetic characters are left unchanged.

    s: str, the string to be encoded.
    returns: str, the encoded string.
    """
    encoded = ""
    for char in s:
        if char.isalpha():
            if char.isupper():
                encoded += chr((ord(char) - 64) % 26 + 65)
            else:
                encoded += chr((ord(char) - 96) % 26 + 97)
        else:
            encoded += char
    return encoded


def decode_string(s):
    """
    Decodes an encoded string by shifting each letter in the alphabet back by one position.
    For example, 'bcd' becomes 'abc', 'yza' becomes 'xyz', etc.
    Non-alphabetic characters are left unchanged.

    s: str, the encoded string to be decoded.
    returns: str, the original string.
    """
    decoded = ""
    for char in s:
        if char.isalpha():
            if char.isupper():
                decoded += chr((ord(char) - 65 - 1) % 26 + 65)
            else:
                decoded += chr((ord(char) - 97 - 1) % 26 + 97)
        else:
            decoded += char
    return decoded




original = "The quick brown fox jumps over the lazy dog."
encoded = encode_string(original)
decoded = decode_string(encoded)

print("Original: ", original)
print("Encoded:  ", encoded)
print("Decoded:  ", decoded)
